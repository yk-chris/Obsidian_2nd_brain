(Strategy) KC + ADX + VP + Pivots
```pin
//@version=6

strategy("KC + ADX Signal + Volume Profile + Pivots Strategy",

     overlay = true,

     max_labels_count = 500,

     max_lines_count = 500,

     max_polylines_count = 100,

     max_bars_back = 500,

     process_orders_on_close = true,

     default_qty_type = strategy.percent_of_equity,

     default_qty_value = 1)

  

// ── Inputs ────────────────────────────────────────

kc1_len    = input.int(50,    "KC1 Length")

kc1_mult   = input.float(3.75, "KC1 Multiplier", step = 0.25)

kc2_len    = input.int(50,    "KC2 Length")

kc2_mult   = input.float(2.75, "KC2 Multiplier", step = 0.25)

atr_len    = input.int(10,    "ATR Length")

  

adx_smooth = input.int(12, "ADX Smoothing")

di_len     = input.int(12, "DI Length")

adx_tf     = input.timeframe("", "ADX Timeframe")

adx_thresh = input.int(30, "ADX Threshold", minval = 1)

  

vp_start    = input.int(200, "VP Lookback", minval = 10, maxval = 500)

vp_bins     = input.int(50, "VP Bins", minval = 5, maxval = 200)

show_poc    = input.bool(true, "Show PoC")

  

show_pivots  = input.bool(true, "Show Pivots")

pivot_len    = input.int(10, "Pivot Length")

pivot_filter = input.int(20, "Pivot Volume Filter %")

  

show_signals = input.bool(true, "Show Signals")

close_on_opp = input.bool(false, "Close On Opposite Signal")

  

use_sl     = input.bool(true, "Use Stop Loss")

use_tp     = input.bool(true, "Use Take Profit")

sl_percent = input.float(1.0, "Stop Loss %", minval = 0.01, step = 0.05)

tp_percent = input.float(2.0, "Take Profit %", minval = 0.01, step = 0.05)

  

// ── KC Calculation ────────────────────────────────

atr_val   = ta.atr(atr_len)

basis     = ta.ema(close, kc1_len)

kc1_upper = basis + kc1_mult * atr_val

kc1_lower = basis - kc1_mult * atr_val

kc2_upper = basis + kc2_mult * atr_val

kc2_lower = basis - kc2_mult * atr_val

  

// ── ADX via request.security ──────────────────────

tf = adx_tf == "" ? timeframe.period : adx_tf

[diplus, diminus, adx_raw] = request.security(

     syminfo.tickerid, tf,

     ta.dmi(di_len, adx_smooth),

     lookahead = barmerge.lookahead_off)

  

adx_strong = adx_raw >= adx_thresh

  

// ── Colour Logic ──────────────────────────────────

col_bull = color.new(color.green, 15)

col_bear = color.new(color.red, 15)

col_neut = color.new(color.gray, 50)

  

kc_col  = adx_strong ? (close > basis ? col_bull : col_bear) : col_neut

bas_col = adx_strong ? color.yellow : color.gray

  

// ── Plot KC ───────────────────────────────────────

p_k1u = plot(kc1_upper, "KC1 Upper", kc_col, 2)

p_k1l = plot(kc1_lower, "KC1 Lower", kc_col, 2)

p_k2u = plot(kc2_upper, "KC2 Upper", color.white, 1)

p_k2l = plot(kc2_lower, "KC2 Lower", color.white, 1)

p_bas = plot(basis, "Basis", bas_col, 1)

  

fill(p_k1u, p_k2u, adx_strong ? color.new(color.blue, 85) : color.new(color.gray, 90))

fill(p_k1l, p_k2l, adx_strong ? color.new(color.blue, 85) : color.new(color.gray, 90))

fill(p_k2u, p_k2l, color.new(color.white, 92))

  

bgcolor(adx_strong ? color.new(color.orange, 93) : na)

  

// ── Signals ───────────────────────────────────────

buy_sig  = close[1] < kc2_lower[1] and close >= kc2_lower and adx_strong

sell_sig = close[1] > kc2_upper[1] and close <= kc2_upper and adx_strong

  

is_long_pos  = strategy.position_size > 0

is_short_pos = strategy.position_size < 0

  

// ── Entries ───────────────────────────────────────

if barstate.isconfirmed

    if buy_sig and strategy.position_size <= 0

        strategy.entry("Long", strategy.long)

    if sell_sig and strategy.position_size >= 0

        strategy.entry("Short", strategy.short)

  

// ── Optional opposite close ───────────────────────

if close_on_opp and barstate.isconfirmed

    if buy_sig and is_short_pos

        strategy.close("Short")

    if sell_sig and is_long_pos

        strategy.close("Long")

  

// ── Exits ─────────────────────────────────────────

if strategy.position_size > 0

    long_sl = strategy.position_avg_price * (1 - sl_percent / 100)

    long_tp = strategy.position_avg_price * (1 + tp_percent / 100)

    if use_sl and use_tp

        strategy.exit("Long Exit", from_entry = "Long", stop = long_sl, limit = long_tp)

    else if use_sl

        strategy.exit("Long Exit", from_entry = "Long", stop = long_sl)

    else if use_tp

        strategy.exit("Long Exit", from_entry = "Long", limit = long_tp)

  

if strategy.position_size < 0

    short_sl = strategy.position_avg_price * (1 + sl_percent / 100)

    short_tp = strategy.position_avg_price * (1 - tp_percent / 100)

    if use_sl and use_tp

        strategy.exit("Short Exit", from_entry = "Short", stop = short_sl, limit = short_tp)

    else if use_sl

        strategy.exit("Short Exit", from_entry = "Short", stop = short_sl)

    else if use_tp

        strategy.exit("Short Exit", from_entry = "Short", limit = short_tp)

  

// ── Plot Signals on Chart ─────────────────────────

plotshape(series = show_signals and buy_sig,

     title = "BUY",

     style = shape.labelup,

     location = location.belowbar,

     color = color.green,

     text = "BUY",

     textcolor = color.white,

     size = size.small)

  

plotshape(series = show_signals and sell_sig,

     title = "SELL",

     style = shape.labeldown,

     location = location.abovebar,

     color = color.red,

     text = "SELL",

     textcolor = color.white,

     size = size.small)

  

alertcondition(sell_sig, "🔴 SELL Alert",

     "🔴 SELL: {{ticker}} {{interval}} — 價格回穿KC2上軌，ADX強趨勢確認")

alertcondition(buy_sig, "🟢 BUY Alert",

     "🟢 BUY: {{ticker}} {{interval}} — 價格回穿KC2下軌，ADX強趨勢確認")

alertcondition(sell_sig or buy_sig, "⚡ KC2 回歸訊號",

     "⚡ KC2 回歸訊號：{{ticker}} {{interval}} — 請確認方向")

  

// ── Pivot Detection ──────────────────────────────

type PivotInfo

    float price

    int idx

    bool isHigh

  

var pivots = array.new<PivotInfo>()

  

ph = ta.pivothigh(pivot_len, pivot_len)

pl = ta.pivotlow(pivot_len, pivot_len)

  

if not na(ph)

    pivots.push(PivotInfo.new(ph, bar_index - pivot_len, true))

if not na(pl)

    pivots.push(PivotInfo.new(pl, bar_index - pivot_len, false))

  

while pivots.size() > 0 and pivots.first().idx < bar_index - vp_start

    pivots.shift()

  

// ── Volume Profile (last bar only) ────────────────

var polyline vpPoly = na

var line pocLine = na

var label pocLbl = na

var pivotLevels = array.new<line>()

  

if barstate.islast

    if not na(vpPoly)

        vpPoly.delete()

    if not na(pocLine)

        pocLine.delete()

    if not na(pocLbl)

        pocLbl.delete()

    for ln in pivotLevels

        ln.delete()

    pivotLevels.clear()

  

    float H = high

    float L = low

    for i = 1 to vp_start - 1

        H := math.max(H, high[i])

        L := math.min(L, low[i])

  

    binSize = (H - L) / vp_bins

    Bins  = array.new_float(vp_bins, 0.0)

    Delta = array.new_float(vp_bins, 0.0)

  

    for i = 0 to vp_start - 1

        mid = (high[i] + low[i]) / 2.0

        b = math.floor((mid - L) / binSize)

        b := math.max(0, math.min(b, vp_bins - 1))

        Bins.set(b, Bins.get(b) + volume[i])

        d = close[i] >= open[i] ? volume[i] : -volume[i]

        Delta.set(b, Delta.get(b) + d)

  

    maxVol = Bins.max()

    if maxVol == 0

        maxVol := 1

  

    pts = array.new<chart.point>()

    pocBin = -1

  

    for b = 0 to vp_bins - 1

        yLo = L + b * binSize

        yHi = yLo + binSize

        pct = Bins.get(b) / maxVol * 100

        w = math.round(pct / 100 * 60)

        x0 = bar_index - vp_start

        x1 = x0 + w

  

        pts.push(chart.point.from_index(x0, yLo))

        pts.push(chart.point.from_index(x1, yLo))

        pts.push(chart.point.from_index(x1, yHi))

        pts.push(chart.point.from_index(x0, yHi))

  

        if pct >= 99.9

            pocBin := b

  

    totalDelta = Delta.sum()

    profCol = totalDelta >= 0 ? color.teal : color.maroon

  

    vpPoly := polyline.new(

         points = pts,

         curved = false,

         closed = false,

         xloc = xloc.bar_index,

         line_color = profCol,

         line_style = line.style_solid,

         line_width = 1)

  

    if pocBin >= 0 and show_poc

        pocPrice = L + (pocBin + 0.5) * binSize

        pocLine := line.new(bar_index - vp_start, pocPrice,

                            bar_index, pocPrice,

                            color = profCol, width = 2)

        pocLbl := label.new(bar_index, pocPrice,

                            str.tostring(Bins.get(pocBin), format.volume),

                            style = label.style_label_left,

                            color = profCol,

                            textcolor = color.white,

                            size = size.small)

  

    if show_pivots

        for pv in pivots

            if pv.idx > bar_index - vp_start and pv.idx < bar_index - 54

                for b = 0 to vp_bins - 1

                    yMid = L + (b + 0.5) * binSize

                    pct = Bins.get(b) / maxVol * 100

                    if math.abs(pv.price - yMid) <= binSize and pct >= pivot_filter

                        lCol = pv.isHigh ? color.maroon : color.teal

                        txt = pv.isHigh ?

                             str.tostring(Bins.get(b), format.volume) + "\n" + str.tostring(math.round(pct)) + "%" :

                             str.tostring(math.round(pct)) + "%\n" + str.tostring(Bins.get(b), format.volume)

  

                        label.new(pv.idx, pv.price, txt,

                             style = pv.isHigh ? label.style_label_down : label.style_label_up,

                             color = lCol,

                             textcolor = color.white,

                             size = size.tiny)

  

                        pivotLevels.push(

                            line.new(pv.idx + pivot_len, pv.price,

                                     bar_index, pv.price,

                                     color = lCol,

                                     style = line.style_dotted,

                                     width = 1,

                                     force_overlay = true))

                        break

  

    for i = pivotLevels.size() - 1 to 0

        ln = pivotLevels.get(i)

        pv = ln.get_y1()

        broken = false

        for j = 0 to bar_index - ln.get_x1()

            idx = ln.get_x1() + j

            if idx >= bar_index

                break

            if high[bar_index - idx] > pv and low[bar_index - idx] < pv

                ln.set_x2(idx)

                broken := true

                break

        if broken

            pivotLevels.remove(i)

        else

            ln.set_x2(bar_index)

  

// ── Info Table ───────────────────────────────────

var tbl = table.new(position.top_right, 2, 5,

     bgcolor = color.new(color.black, 30),

     border_width = 1)

  

if barstate.islast

    table.cell(tbl, 0, 0, "ADX", text_color = color.white, text_size = size.small)

    table.cell(tbl, 1, 0, str.tostring(adx_raw, "#.##"),

         text_color = adx_strong ? color.lime : color.red,

         text_size = size.small)

  

    table.cell(tbl, 0, 1, "+DI", text_color = color.white, text_size = size.small)

    table.cell(tbl, 1, 1, str.tostring(diplus, "#.##"),

         text_color = color.lime, text_size = size.small)

  

    table.cell(tbl, 0, 2, "−DI", text_color = color.white, text_size = size.small)

    table.cell(tbl, 1, 2, str.tostring(diminus, "#.##"),

         text_color = color.red, text_size = size.small)

  

    table.cell(tbl, 0, 3, "KC2 Upper", text_color = color.white, text_size = size.small)

    table.cell(tbl, 1, 3, str.tostring(kc2_upper, "#.####"),

         text_color = color.white, text_size = size.small)

  

    table.cell(tbl, 0, 4, "KC2 Lower", text_color = color.white, text_size = size.small)

    table.cell(tbl, 1, 4, str.tostring(kc2_lower, "#.####"),

         text_color = color.white, text_size = size.small)
```
