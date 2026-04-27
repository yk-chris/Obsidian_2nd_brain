---
title: "KPI Overview Page in Power BI that left my Client speechless"
source: "https://www.youtube.com/watch?v=CzBwMquUz9Y"
author:
  - "[[How to Power BI]]"
published: 2026-02-09
created: 2026-04-25
description: "Join my Power BI Transformation Traininghttps://datatraining.io/powerbidesigntransformationLet my team develop your reports to instantly gain momentumhttps://datatraining.io/powerbi-report-launch"
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=CzBwMquUz9Y)

Join my Power BI Transformation Training  
https://datatraining.io/powerbidesigntransformation  
  
Let my team develop your reports to instantly gain momentum  
https://datatraining.io/powerbi-report-launch  
  
Download file here https://datatraining.io/powerbi-how-to  
  
\--------------------------------  
📊 TRAININGS 📊  
\---------------------------------  
  
Power BI Design 4 Weeks Transformation Program https://datatraining.io/powerbidesigntransformation  
  
Power BI PL-300 Certification Training  
https://datatraining.io/powerbi-pl300  
  
For Custom Trainings and Consulting email directly support@datatraining.io  
  
\---------------------------------  
😍 JOIN 😍  
\----------------------------------  
Join https://bit.ly/4b453bi  
Subscribe https://bit.ly/31MnQGO​  
Insta https://www.instagram.com/howtopowerbi/  
LinkedIn https://www.linkedin.com/in/basdohmen/  
TikTok https://www.tiktok.com/@how.to.power.bi  
X https://twitter.com/HowToPowerBI  
fb https://www.facebook.com/groups/howtopowerbi  
Threads https://www.threads.net/@howtopowerbi  
Newsletter https://datatraining.io/newsletter  
  
\---------------------------------  
👇 CHECK THIS OUT! 👇  
\---------------------------------  
💻 My gear https://amzn.to/47F21Yc  
📚 Power BI books MUST READ! https://amzn.to/3tUfFcj  
💡 General books I recommend https://amzn.to/48YNo33  
🎶 Music for my videos https://www.epidemicsound.com/referral/8pjcbj  
🚀 For growing on YouTube: https://www.tubebuddy.com/bas  
🏄 Stuff I use daily https://amzn.to/3HqfMQ2  
  
\* Above are affiliate links, which means at no additional cost to you, if you make a purchase using these links we will receive a small commission. It supports us and helps us to continue making more How to Power BI videos!  
  
Thanks for being a part of this channel and all your support! 💪 🙏  
  
#HowToPowerBI​ #PowerBI​ #DataTraining​  
#powerbidesktop​ #powerbitraining​ #powerbideveloper​ #DAX

## Transcript

**0:00** · There's one request that I get on almost every PowerBI project \[music\] and that is to create an overview page of all the KPIs so that they can quickly see what is working and what is not working. Now, in this video, I'm going to show you exactly that, how to create a beautiful KPI overview in just a few steps. Let's dive in. This is actually a really good use case for the scorecard visual.

**0:22** · However, there we are kind of limited to what shows and how it shows and therefore I often need to have an alternative and that is this visual over here. It's built using a card visual.

**0:34** · You see, we have all of our metrics. We apply conditional formatting using a nice gradient to see how close we are to the target. Plus, we use some SVGs for that little data bar in the bottom right corner. All right, now let's create this visual in just a few steps. We're going to start off with a new card visual form. It's not new anymore. It's now generally available and replace the old card. Okay. Now, I'm going to make this much bigger, almost as big as the page and put it over here at the center.

**0:58** · Now, what most people would do next is to go straight away to the data pane and start adding all of their KPIs, the measures one by one. Now, if you do this, then you're adding cards. Meaning, if you would go to the formatting pane, then you would see the category options blended out. However, you would then have your card options to change the formatting.

**1:20** · Now, the difficulty with this approach comes when you want to add the conditional formatting to the call out because then you have to set up the conditional formatting one by one for all of the different series that you're working with and that is something that we want to avoid. And also here we do not only have conditional formatting, we also want to add these data bars which are SVG images. So, I'm going to take a different approach.

**1:44** · I'm going to go back to the builds panel, take this out, and instead of this, we're going to create a small helper table, which you could do by going to home, and then enter data, and then here, just create two columns, one with your KPI name, and then another one with the KPI description. And then you fill out all of your KPIs one by one. And then over here, the table name, just pick a nice name like KPIs, and then load. Now, here you see my version.

**2:10** · And this can be a disconnected table.

**2:12** · All right. Now I'm going to go back to my report and here we're going to use from that new KPI table the KPI name onto the card visual. Now you see the big difference from before is now if we have many different categories but each one of these categories has only one card and that is also reflected here in \[clears throat\] the formatting pane multicategory layout and category header is not grayed out anymore formatting options but the real benefit will only come later when we start applying conditional formatting and the SVGs.

**2:42** · Now the next thing that we need to do is change the grid. All right. So, we have to go to multicategory layout layout.

**2:51** · And over here, let's go for tiles and we want to have a grid that is 3x3. All right, I'm going to make it a little bit bigger. Of course, we also need to show our KPI values. Now to do that we have to go back to our data pane and then here I have one measure that's called KPI value which basically pulls in the right measure for each KPI that are listed in this disconnected table that we just created before. All right. Now this measure we can add to our card visual on values and ta there you go.

**3:22** · So all of our KPI values now show unless you made a typo in the measure versus how it's called in your disconnected table. And so watch out. And the next thing that we can do is well first let's get rid of that label for the call out.

**3:39** · So I'm going to go here turn the label off. And then I want to create this nice double header that we have over here in the solution. So where we have the KPI name then right underneath it I want to add extra information which could be the description. All right. Now to do that is actually kind of tricky because let's go back. Now the problem is that if we go to category header and then title there's no subtitle and also the cards don't have this functionality built in.

**4:08** · All right. So what are we going to do instead? Well let me show you. We are going to take our headers and put them here on the left hand side. And then we simply make them disappear. We're going to make them invisible. Now, how do we get the double headers? We're going to do that using reference labels. So, with reference labels, well, there we can just add as many lines as we want and we're going to put them over there at the top because now we can easily change the layout. What do we want first? The color, the reference, or the image.

**4:38** · All right. And then well, it's a matter of formatting because then we can have our double lines here at the top, our call out, and then later on the image there.

**4:50** · All right. That sounds like a lot.

**4:51** · However, actually, it's just a few steps. Stay with me. Let's go to the category header. And then here we have layout and we're going to choose left.

**5:01** · Boom. Step one. Now, that messes up the whole card. However, now if we go to title, we can put the orientation to rotate to 70 or 90. doesn't really matter. And I would also make the font small and then put the transparency to 100%. Boom. Now, if we scroll a little bit further down there, we have background also off. And now you see here to the left of the card, but still within the category on the left hand side, we have this empty space where the header is. Now, it's quite a lot at the moment. So, I put the padding here to zero. Okay.

**5:31** · And then we don't want to have the border around the categories anymore, which we can turn off here on the multicategory layer. Turn it off. So now we are left with just seeing the guards within each category. Okay. Now if you want to decrease the gap a little bit further, then we just go to gap, put it to zero, and now it looks better. All right. So we got rid of the \[clears throat\] headers, but we still want the title and subtitle, which we can do in the next step.

**5:58** · Now we're going to scroll further down all the way to reference labels. And there we have to choose a series KPI value. And I want to have just let's say the KPI name and description. Boom. Boom. And then for all of the labels, we don't want to have the title. We also want to have a little bit smaller maybe. And maybe not that bold. And if you want to fine-tune it a little bit further, make the description a little bit distinct from the name.

**6:27** · Then we just have to select that label value, make it cursive, maybe even a bit smaller. You get the idea. Here it's not visible because I have to stretch up the visual a bit more but you see it's there. If you want to get rid of that gray background that is here in the reference labels layout background off.

**6:45** · Now you see there's also a bit of misalignment on the left hand side that looks like padding. Yep, there we have padding. Let's put it to zero. Now I want to change the order. I want to take these reference labels and put these reference labels first. We have to go for that to \[music\] card. Yes, for me it also sometimes takes a little bit of a search to find the right setting. All right, so we go to cards layout and here we have the order.

**7:14** · And first I want to have the reference label, then the call out, then the image. And here you can also fine-tune the call out size and maybe make it a little bit bigger. For example, 60%. Okay, now that goes in the right direction. Now, here for the cards, I don't want to have this divider. Oh, you can also leave it on if you like it, but I'm going to turn it off for this example. Now, this definitely goes in the right direction.

**7:38** · Of course, along the way, keep on fine-tuning. For example, if you want to have these reference labels a little bit closer or further away from each other, then you just go to the right section, reference labels, layout, padding, and there we have uniform padding, which you can make either bigger or smaller, right? Um, also keep in mind there's this call out uh size, right? So if you go too far at some point it probably would not fit anymore. See that's not visible. Then you would have to make the call out area smaller. All right.

**8:06** · By doing these type of exercise you really get good control over that card visual because there are many options now.

**8:14** · Right. So I'm just going to put it to zero. And now it's time to apply conditional formatting to all of our KPI values. And we want to compare them to our targets, to our goals. So I have already measured that up. Let's have a closer look. Now here you see I'm just comparing the KPI value to the goal. I'm dividing the actual by the goal. And if it goes over one, then I want to cap it at one. If it goes below zero, then I want to cap it at zero. All right? So that's why I called this variable cloud.

**8:45** · All right. Now that value that's between zero and one I then use to basically apply a gradient scale to my color and here we have the color model. Now if you want to really dive in a little bit deeper into colors and how to how that works with with DAX and the different color models that you can choose from then check out uh this video over here.

**9:08** · Okay, good. Now you see I'm basically then taking that clamp value between 0 and 1 plugging it in here to calculate the U that goes from 280 to 168. So from purple to the all these other two inputs in this color model I leave the same.

**9:25** · Okay. And you can also play around with the transparency if you want that. Let's now use our conditional formatting measure on our visual. Now before we do that, let me just make sure that one month is selected for our KPI. So let me just take my month fields filter on all of the pages select the last month.

**9:42** · Okay, perfect. So I'm going to take my visual go to formatting then call out and then over here you see we have value and then that X button and then we want that field value. I'm going to select that measure that we set up. So here we have color actual value and that doesn't look too good does it? Now I wasted a lot of time going back to the measure and figure out what did I do wrong.

**10:11** · However, it's actually formatting problem. Let me show you. I'm going to go here to card. You see we can choose all or KPI value. And this is actually important for that measure to calculate correctly otherwise it wouldn't calculate within that right filter context. So you have to really select the series KPI value. Then go over here to value FX. Then here we have field value. We look for a measure again visual actual value and click okay. And this time yes it's working. Okay.

**10:42** · So I hope this saves you a lot of time figuring out debugging the measure that is actually working. Okay. Just a small formatting thing that you have to watch out for. So the green ones there we had our target. the dark purple ones there.

**10:59** · We are still quite far away from our target. Probably a good idea to add a legend there at the end as well. Okay.

**11:06** · Building really good PowerBI reports isn't about simple tricks or making things look pretty. It's about knowing exactly what needs to go in your PowerBI reports and how to best visualize it and of course having the technical skills to do so. Now, my team and I have helped hundreds of companies across all different kinds of industries build effective PowerBI reporting solutions.

**11:25** · Now, if you want to learn all of our processes, frameworks, and get our templates of how we do it, then check out our upcoming PowerBI design transformation over here. I hope to see you there. Let's go back to the video.

**11:36** · All right. So, we have our KPI overview.

**11:39** · We have double titles. The main KPI shows with a description underneath it.

**11:43** · We have conditional formatting applied to the KPI values using a nice gradient scale. The last missing piece is then the data bars and that we're going to do with SVG images. Now, let's first apply these SVG images and then I will show you the SVG. It's maybe the easiest and quickest way to approach it. All right.

**12:02** · So, I'm going to go back to our card visual. Now, here don't go to image because if you would do it from here, then it's going to add the images underneath it, which is not what I want.

**12:12** · I want to have it on the right hand side of the of the call out. So, I'm going to go to call out and then from here we add the images. Okay. So, let's open it up.

**12:22** · We can then select from data and then here I have already a measure an SVG measure and on first side this looks bad and it's again one of these situations where I was not careful and you really have to watch out what you're applying these images to and if we go to apply settings you see all cards so it's a similar situation as what I just had with the conditional formatting you don't want to do it here but you really want to do it for the KPI value so that the right field context of the KPI and the image shows correctly.

**12:54** · So let's turn it on. Let's do this again. Select from data and over here I want my SVG measure and that looks well not beautiful yet.

**13:06** · However, at least the right SVGs show in the well not the right way but they show correctly. So now we just have to fine-tune it and say I want this to fit nicely. I want to have it on the right hand side of the text and I want it to be much bigger. So the image area size we can increase to for example 60%. All right. And now it actually looks good.

**13:30** · Now of course we can fine-tune it a little bit more but it is working now correctly. Now let me also show you that SVG so that you more or less know how it's set up. First of all I went over here to the text review and here you see my SVG actually has only four parts. We have two rectangles defined over here.

**13:50** · Rectangle one, rectangle two. We have a small vertical line and we have a text or the data label. That's it. So here you see when we have a value that's below the target, below a goal, we have one bar, that's the purple part. Here we have the gray part, that's just kind of the area until the target, the goal.

**14:13** · Then we have that vertical line. And we have the data label. That's it. Now, if you go back to this UDF, you see that's all defined here. And the scaling of the bar, how big everything needs to be and where it should be. Well, that's defined over here using the inputs into the function.

**14:31** · And just like with the conditional formatting, we are comparing the actual value to the target value, the goal value, which if you divide one by the other gives us a proportionate amount, which we can then multiply by the SVG width that we decide on here as input in our function to say how big that bar should be relative to the overall width of the SVG. And the same thing we do also for that little vertical line.

**14:58** · So we just have over here calculation for where that line should be when the goal is under or above the target. That's it. Looks kind of complex on first sight, but really if you just go to this video where I walk you through it step by step, then it all makes sense. It's really not as complex as it uh as it looks like on first site.

**15:19** · In the future, you just reuse this UDF, right? So you only have to go through this effort once. So that UDF is then used over here in this measure where I give it all of the inputs that it needs and the SVD width and height um the KPI value, the target and the colors that should be applied. I used a different uh color there for the goal just to make it a little bit darker just because otherwise it wouldn't stand out if it would overlap the filled data bar underneath it when the actual is higher than the dark. All right, that's basically it already.

**15:50** · Now the only thing that's kind of missing is a legend. You still need a legend otherwise people don't know what is green, what is purple, right? So green is when we really reach the target, right? And purple is when when we're still far away from it and then everything in between.

**16:06** · Well, then we go just go from purple to green. Okay. So to create this legend, we need also a custom way to set that up. And yeah, SVG is again kind of the way to do it. just ask claw to create it quickly for you, which is exactly what I did to get to this result. It worked. It barely double checked it. So over here, just put it in. Now to visualize this measure, just make sure that if you're using SVG measures, always set the data category to image URL. Then we can just drag it into our report. Switch to the new card visual. Okay.

**16:38** · And now we want to visualize that image. No, we can just go here to call out image turn it on select from data and then just like before and we can select our SVG measure. Now over here it's very small but and we don't need the label and value. So we can get rid of that and we can size it nicely. 200 is a little bit much. Let's start smaller. Maybe 50.

**17:06** · Still too much. Maybe 40h almost. 35 maybe better. And you see now we can just resize it. Get rid maybe also of the border around it. This is the border of the card. And you don't need stuff like background. And you can also turn that off. Okay. Then it's just resizing it and putting it wherever you want it to be. Now this needs a little bit of text as well because what is this zero to 100% goal attainment or something like that.

**17:34** · And so we can go to insert text goment make it smaller. So for example font size eight and then I put this just right in front of it right above it wherever you want it to be. Okay. And that's it. We have a beautiful KPI overview here in our PowerBI report. If you like this video, check out these two over here.

**17:58** · If you want to build PowerBI reports together with me and learn all of my tips and tricks and how I approach it on real PowerBI consulting projects, then check out my upcoming PowerBI design transformation program over there. Thank you for watching. See you in the next one.