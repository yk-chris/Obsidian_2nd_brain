---
title: "Making DAX Easy"
source: "https://www.youtube.com/watch?v=sOMhqaaWM9Y&list=PLs93rgE5erT5RbRBI20YjfuJvUNXnEyww"
author:
  - "[[How to Power BI]]"
published: 2022-02-27
created: 2026-04-26
description: "5 things you need to know about DAX. After knowing these main concepts DAX started to make sense to me and I'm sure it will for you too. It is high time to make DAX Easy to everyone!Enjoy this video"
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=sOMhqaaWM9Y)

5 things you need to know about DAX. After knowing these main concepts DAX started to make sense to me and I'm sure it will for you too. It is high time to make DAX Easy to everyone!  
Enjoy this video and subscribe to always stay updated on my favorite Power BI tricks!  
  
Download file here https://datatraining.io/powerbi-how-to  
  
\--------------------------------  
📊 TRAININGS 📊  
\---------------------------------  
Power BI Design 4 Weeks Transformation Program https://my.datatraining.io/pages/powerbidesigntransformation  
  
Power BI Essentials https://datatraining.io/powerbilearningpath  
  
Business User Training https://datatraining.io/powerbi-business-users  
  
For Custom Trainings and Consulting email directly support@datatraining.io  
  
\---------------------------------  
⏱️ TIMESTAMPS ⏱️  
\---------------------------------  
00:00 Intro  
00:50 1. Filter context & calculate  
04:47 2. Variables  
06:51 3. Row context  
08:25 4. Context transition  
13:31 5. When to use a measure vs calculated column  
18:10 Putting it to practice  
19:44 End  
  
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

### Intro

**0:00** · why is it not working are you frustrated because your dex formulas are not working or you want to learn dax but you don't know where to start well in this video i'm going to show you five different concepts that make decks easy or at least easier now let's get started \[Applause\]

**0:27** · welcome to how to power bi my name is boss and if this is the very first time for you visiting this channel then make sure to hit that subscribe button if you want to stay up to date on all of my videos in which i share everything i know about power bi so buzz could you quickly explain how dex formulas work but dex formulas at the beginning can be quite tricky however just knowing a few main concepts will make it a lot easier

**0:48** · and that's exactly what i'm going to show you right now let's dive in straight away with the first example which is fill the context and how to modify the filter context using the calculate function now for example we're going to use this data model here where we have a sales table and three dimensions one for customer one for product and one for the dates now let's start off by creating a matrix visual to which we are going to add the total sales now that gives us 17910 which has no filter applied to it

### 1\. Filter context & calculate

**1:15** · so it's the sum of all of the sales transactions that we have in the sales table but now we can create a breakdown for example by the customers so i go over here to my customer table take customer and put it onto the ros and now we have filter context on the customer name so that first value 2523

**1:32** · only includes those sales transactions for alice now if you compare that to excel you could get to those numbers using the sumif function or using a pivot table now i could add further to the filter context by adding more fields to rows or columns so let me take for the category put it in columns and now we have the filter context determined by the customer name but also the product category but the filter context is not only determined by what you have as breakdowns for your visual also the filter could come from across

**2:02** · filter interactions from a different visual for example here we have a bar chart if i click here on q121 now you see that we also have an axle filter on the dates or the filter could also come from the filter panel so now that you know what the filter context is you need to know how to add a filter or modify the filter within your measures using

**2:21** · the calculate function so for example you want to calculate the difference between two product categories let's say hair care and makeup now i'm going to take out the product category from columns and now we're going to add a new measure and let's call this one total sales hair gear and here we're going to start off with the calculate function so here we have two parts the first part calculates the sum of sales so that's the expression and the second part there we can add filters or change the filter context so

**2:50** · let's start with the first one and i already have a measure that calculates the sales so we i refer to that one and then the second part there we can add a filter now i want to have a filter on the product category so let's select for the category and say that it needs to be equal to hair care so here here and then i can close the calculate function and let's now add it to a matrix and you see we have the filtered amounts

**3:18** · for that specific product category now the same thing i can do for makeup now so let's copy it insert a new measure and here we can then replace hair care with makeup and then we can also add this one to the matrix and now we just have to calculate the difference between the two so that's going to be the third measure and this is going to be the sales difference makeup versus hair care and we can just refer back to the measures that we just created before so we have

**3:46** · makeup minus the hair care sales now what could be a little bit confusing at the beginning is when the fields that you are modifying the filter off inside of the calculate function is also being used to create the breakdown in your visual now for example if i replace customer name now with the product category let's do that

**4:06** · then you see we have the same value for hair care on all the rows and the same form make up and the difference and that is because the calculate function overrides the filter that we have coming from the visual on product category so for example over here where we have total sales hair care we are on the roll for product category makeup that's the filter context that comes from the visual the calculate function replaces that filter with product category hair care and that's why we see the same value everywhere so that we can compare

**4:33** · all of the sales to the sales that come from hair care another thing that you're probably wondering about is do you really need three measures to calculate the sales difference between two product categories well no we could do everything in a single measure using variables and that's the next thing that you need to learn so let's rewrite the measure but now using variables now the first variable is going to contain the sales for the hair care products

### 2\. Variables

**4:58** · and i copy over what we wrote before and then we do the same for the makeup sales so let's copy that over and then over here we place hair care with makeup so now we just have to calculate the difference which we can also store in a separate value so sales result is going to be equal to the sales difference between sales makeup minus sales hair care now if you use variables then you need to have a return statement in the end and what do we want to return well the

**5:27** · result variable all right so now we have done everything in one measure and this also makes it a little bit easier to check intermediate results for example you could take the variable sales hair care return that one see if those values are correct and then continue with the next part of your calculations so that you step through it one by one ac values are still the same however now you've done everything in just one measure now one thing that you have to watch out for is that variables are not really variable but more constants now let me

**5:54** · show you what i mean so here i'm going to create a variable for sales which is equal to the measure total sales now the value gets calculated at this point in your measure and later on it will not change anymore so that means if i would use the

**6:12** · variable over here inside of my calculate function then it wouldn't change over here the product category to hair care anymore because well the value has already been defined here at the top so if i also change that for sales makeup and go back to my matrix visual then you see the difference is zero and that is because we assign the value for the sales variable here at the top and it is not

**6:35** · really a variable so later on we cannot change that anymore with the calculate function so what we end up doing is taking the total sales minus the total sales is zero so now you know what is filter context and how to change the filter context using the calculate function you know about variables the next thing is row context now for that we go to the sales table so here we have the quantity we have the price so we can calculate the sales just by multiplying one with the other and we have to do that roll by roll and if you add a

### 3\. Row context

**7:03** · column to a table then there's automatically raw contacts now let me show you i click here on new column and we can call this new column sales where we multiply the quantity with the price

**7:18** · and then with a dot of cs measure i could simply take the sum of that sales column easy however you don't necessarily need to create that column now let me try to do the same now with a measure and here we want to multiply the quantity with the price so as soon as i start typing quantity nothing pops up and that's because it doesn't know for which table you want to do this calculation roll by row four

**7:45** · and that's why we have iterator functions so that we can introduce row context now let me show you over here we have for example some x but there's also average x count x max x which lets you lets you iterate over a certain table now that table in this case is fc sales so we go row variable over the table and

**8:07** · then for each line we want to take the quantity and now you see it does pop up over here we can select it and multiply it with the price now you see our total sales values didn't change however now we don't need to store that whole new column in a data model which keeps data model a bit smaller so now we're at number four which is context transition turning raw contacts into filter context now let me show you what that mean in the customer table i'm going to add a new column

### 4\. Context transition

**8:33** · and let's say we want to calculate the total sales amounts for all of these customers that we have here then here we can say total sales by customer and here we want to have the sum of sales so i use a sum function and take the sales column from the total sales table and returns exactly the same sales amount for each customer now what is that sales amount it's basically just the sum of the total sales column in our

**8:59** · sales table but why is the same well because there's no filter context it doesn't automatically take that customer as a filter for the sales amounts so we have to use that role as a filter so we have to do context transition turning raw context into filter context and the way to do that is again this calculate function so we can wrap this inside of a calculate

**9:25** · and boom there you go we have the total sales month by customer so the calculate function can also force context transition meaning turning raw context into filter context now another way to achieve that is to first create a measure which we already have total sales and if i use the measure total sales then you see we also get the correct amounts and that is because a measure automatically wraps the expression inside of a calculator so this would be

**9:54** · the same thing so if i wrap this inside of a calculate you see the values don't change it's implicitly already there it's just nobody would write it like this okay and you would just refer to the measure now this was an example where we added a column to a table but can context transition also be used within a measure well yes let me show you now let's say that we want to calculate the average of the total sales by customer now if i

**10:23** · add a new measure and here we want to have the average sales by customer then i cannot simply use an average function and then refer to the sales why not now let me show you now you see we have very low amounts because these are the averages of all of the sales transaction amounts so the

**10:44** · level of detail that we have in the sales table is not by customer it's by transaction and that's why we have such a low values so we first need to aggregate the total sales at the customer level and of those values we want to calculate the average now how can we do that well we need to go row by row over the customer table calculate the total sales and then of those values we want to have the average so that is an average x function that we need where we want to iterate over the customer table so we have dim customer

**11:17** · and row by row we want to calculate the total sales amount now here we have the measure but let me first write here the sum of the sales that we want to calculate and then close the average x function and that's it now it's not correct yet but let me show you why now here you see that our measure returns exactly the same values as the total sales measure and that's because we still have two problems the first problem is that there is filter contacts now on the customer

**11:48** · name which we didn't have before in the customer table now the second problem is that we didn't force context transition now that means that we are iterating the customer table but this filter contact so we are only iterating one row there for alice alice row and then we calculate the sum of

**12:07** · sales which is exactly the same as the total sales month over here in that first measure and then you take the average of just one number which is then the same all right so how can we do it the correct way let's go back to our measure now first of all we have to remove the filter context on the customer table which we can do with all function so it returns all the rows in

**12:28** · the custom table and then the second thing that we need to do is that we need to force context transition which we can do with the calculated function so over here calculate break it open break it close or remember alternatively you can just refer to the total sales measure would also work and now you see we have the average sales amount at the customer level and so when we are here

**12:51** · at the alice role well the filter context is customer name equals alice however with the all function we return the whole customer table then we go row by row calculate the total sales which we do with context transition and of those 10 values we calculate the average and that happens row by row and so for ariel exactly the same it removes the

**13:14** · filter context scenario gives us the whole customer table iterates over the 10 rows and of those calculated total sales values and it takes the average and then as a natural next step you could for example take those total sales values and compare them to the average sales at the customer level so now we at the last point point number five when to use a calculated column versus a measure now let's first start when you really need to have a calculated column and that is when you want to create a breakdown or use a certain categorization as a filter so let's add

### 5\. When to use a measure vs calculated column

**13:46** · a calculated column where we want to categorize the customers to see if there are big spanners or small spanners all right so i'm going to click here on new column and let's call this one big spanner equals and here we can use this if function and we want to check if the total sales by customer is bigger than 2000 done well it's a big spender so let's say pick spender and

**14:13** · otherwise a small spender so now that we have that column we can go to our report and then on the slicer we put the big spender calculated column and now you see we have a slicer which allows us to switch between the big spanners and the small spanners or a different example when you have a column chart like this one and you want to create a breakdown then you also need a calculated column so we take a big spanner calculator gonna put it on the axis and you see we have a breakdown this is not possible within measure so this is when you really need a calculated column but when would you

**14:43** · then really need a measure well if you want to calculate proportional amounts of percentages then you always need a measure now let me first show you the wrong way to do it and then the correct way so here i am in the sales table and i want to express the cost as a percentage of the sales so i'm going to add a new column and let's call this one cost percentage of sales

**15:05** · and here we can simply divide the cost amount so the total cost and divide that by the sales amount so over here we have the total sales all right so row by row everything looks perfect now let's use that new column now on a

**15:24** · visual so i go back to the report view and then i add our new calculated column to the matrix and now we have very large values now what is going on well we calculated the percentages row by row and we are simply summing up those percentages for each customer which is of course wrong now the wrong way of solving this is to go now over here to

**15:45** · that calculation and change it to an average now these values they kind of look correct and they probably close however they give an equal weight to each sales transaction which is wrong and you want to have a weighted average now let me show you an example to clarify that a little bit further now here we have two transactions where we have the cost amount the total sales amount now to get them to the cost percentage of sales we could simply take the cost divided by the total sales and therefore we have over here 10 divided by 20 is 50 percent and here we have 25

**16:16** · divided by 125 now what is then the overall cost percentage of sales well one option would be to say okay i take the average of these two which is what we currently did in power bi however then you don't consider the different amounts of the sales transactions because over here for the second one we have way larger values so it should weight much more and if we just simply take the average we get the wrong amount so what is then the correct way of calculating this is as follows we have to first take the sum

**16:46** · of cost and then divide that by the sum of sales and that would be then the weighted average and this is something that you cannot do with a calculated column you have to use a measure so let's write this measure so let's call this one cost percentage of six

**17:03** · which is then equal to the sum of the cost so over here we have the cost column we sum it up and we want to divide that by the sum of the sales so over here we have the sum of sales then format it as percentages and also add it to your table you see the values are close but they are a little bit different and these ones are the correct amounts because if i now take over here the customer 6834 divided by the 179

**17:33** · well that is 38.16 not this 37.8 so with percentages or proportional amounts that you want to calculate you have to use measures now for some calculations you can get to the correct results with either a calculated column or a measure what should you do then now here the go to advice is that you should use the measures so that you don't have to store an extra column in your data model however of course there are sometimes exceptions to this now for example for our total sales calculation

**17:59** · we got to the correct result with a measure but also with the calculated column so then we added choice so now you have seen five different concepts that make decks a lot easier once you understand them very well now the next step is to build further omnics to explore more functions and the use cases

### Putting it to practice

**18:15** · and let's do one example where we calculate the percent of total now i'm going to insert a measure and let's call this one sales percentage of total now for this calculation we need the total sales for customer and the total sales of all the customers so we can create a variable where we say sales all customers now we have learned the calculate function to change the failed context that we can remove any filter on the customer table so we can say calculate

**18:45** · we want to calculate total sales and we want to remove the filters on the customers now this is a new function which removes the filters i could leave it like this but then it will remove any filter however i only want to remove the filter

**19:00** · on the customer name so i fill in the column customer name all right so that's the first part then we could check okay is this part already working so i want to return sales out customers i see it returns the total for every customer okay so that's good that's the first part that we need and now we need to take the total sales divided by that amount and that's it so i go back to measure and here we can create a variable for the sales percentage of total which is then equal to where we

**19:29** · can save divide and we want to divide the total sales by the sales of all customers so over here we can refer back to that variable then we just have to return that last variable and that's it and you see we have our percentages so this was a quick run-through of all of the main concepts that you really need to master and decks will become a lot easier now if you want to get started straight away with practicing because that's the best way to learn then check out this video now

### End

**19:55** · if you have any questions then post them in the comment section below thank you for watching and see you in the next video