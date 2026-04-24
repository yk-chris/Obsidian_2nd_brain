---
title: "3 Ways to use Calculation Groups You Need to Know"
source: "https://www.youtube.com/watch?v=ZOOdmUCO3m8&t=552s"
author:
  - "[[How to Power BI]]"
published: 2024-01-03
created: 2026-04-24
description: "Join my Power BI Design training here: https://my.datatraining.io/pages/powerbidesigntransformationIn this video I show you 3 less known ways of using Calculation Groups in Power BI. Enjoy this vide"
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=ZOOdmUCO3m8)

Join my Power BI Design training here: https://my.datatraining.io/pages/powerbidesigntransformation  
  
In this video I show you 3 less known ways of using Calculation Groups in Power BI. Enjoy this video and subscribe to always stay updated on my favorite Power BI tricks :)  
  
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
01:06 Example 1  
04:49 Example 2  
10:47 Example 3  
19:15 End  
  
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

**0:00** · calculation groups in powerbi are amazing they basically let you create Dex patterns that you store in calculation items and those patterns you can apply to any measure you like in this way you don't have to write that many measures you can work much more efficiently in power be now time intelligence is a very common example of how to use calculation groups but in this video I'm going to show you three ways in which you can use calculation groups that you might not have seen before let's Dive In all right now the

**0:30** · most common example for calculation groups is time intelligence because for almost any powerbi report you need calculations like year to date or year over year or the percentage growth rate month over month and if you have to write all of these different alternatives for many different main

**0:47** · measures like sales and forecast well that multiplies very quickly and with calculation groups you just write the pattern once and then you apply it to the main measures which can save you a lot of work and a lot of measures but of course there are also other ways in which we can use these calculation groups and we're going to have a look at three of them the first example that I have for you is to use calculation groups to calculate the summary statistics for different measures now let's take for example sales now over here total sales broken down by product subcategory now one option that we would

### Example 1

**1:19** · have is to create separate measures one measure over here that calculates the average one for the max one for the Min one for the total sum now these measures we can then take and add to the table one by one now if we want to do exactly the same thing for let's say the discount well then we would have to write another four measures just like this and if we want to do it let's say for the forecast as well another four and that multiplies very quickly now instead of doing it like this we can make use of calculation groups so let me

**1:50** · take those measures out again and now we go to the modeling View and then over here on the right hand side we have now the data panel where we see tables and model and from here we can add new calculation groups so for this you need to be on the November version or later and need to have it turned on under preview options okay now let's click here on the three dots then choose new calculation group now the first calculation item we can call sum and

**2:19** · over here we cannot just take the sum of the selected measure that doesn't work because over here the selected measure Returns the value of the measure that you applied calculation item too however instead of that what we can do is make use of a sum X and here we can iterate over the main fact table where we have the fields for which we want to calculate the summary statistics so this could for example be here the sales table so I'm going to iterate over my sales table all right and then I want to

**2:52** · calculate over here the selected measure all right and that's it now we have to repeat this three more times I also want to have the average Max and Men all right there you go here we have the calculation item for the average Max and men and now we just have to rename the

**3:08** · calculation group let's call this one summary statistics and the column in that table we can just call aggregation all right now let's use that calculation group in the table from before so I'm going to go back to the report view now to apply the calculation items that are inside of this calculation group to total sales we need

**3:28** · to add the calculation group to the filter context now how can we do that we can make use of the filter panel or we can also add a slice it to the right of it so let's add a slicer to the right of our table and then on that slicer I'm going to add the aggregation column that holds the calculation items and now we can simply click on the calculation item that we want for example the average and you see now over here we have the averages and it can switch to the maximum the minimum or the total sum

**3:57** · that we started off with and now you might think think well that didn't save me much time because I still had to write four calculation items that I applied to that measure however the beautiful thing is that we can now also use the same patterns for different base measures so if I slide this a little bit more to the right all right and then also add maybe the total discount next to the total sales then those patterns

**4:21** · will also be applied to the total discount measure so let's switch here to the average and now we also have the average discounts for the different product subcategories and if I want to see the max I simply click on the calculation item Max using that slicer without having to write separate measures that I showed you before and that can save you a lot of measures so

**4:42** · instead of that we can just use the Dax pattern and apply it to any measure we like all right time for number two we can also use calculation groups to activate a relationship now let me show you how this can be helpful for this we first have to go to our data model and here we have to zoom in on the relationship that we have between our dat table and FC sales now let me double click on that relationship line now here you see that relationship is based on the order date so that means if we show in a visualization the sales broken down

### Example 2

**5:13** · by year it will show the sales amount in the year it was ordered but what if you want to show the sales amount based on the year it was delivered well then we would have to change that relationship for example to the delivery date now there can only be one relationship at a

**5:31** · time and that can be problematic if you want to sometimes show it based on the delivery date and sometimes based on the order date however with calculation groups we can make this much easier so for now let's first create that relationship based on the ordinate click on okay and now we can make a second relationship so we can take date a second time and drag it here on the

**5:56** · delivery date column now you see that new relationship looks a bit different it has a dash line and that means it's inactive doesn't really do anything until you activate it and that you can do in a measure now let me show you how that works I'm going to go back to the reort view I'm going to add a new measure and this one we can call total

**6:16** · sales and over here we are going to use a calculate function where we say we're going to calculate the total sales however now we're going to use that inactive relationship and for that there's a function called use relationship now over here we can specify the two date columns so over here we have the delivery date from the sales table all right and that one needs

**6:44** · to be connected to the date table where we have the date key column or the date column just like this all right so instead of using that active relationship based on the ordinates it will use the inactive relationship that is based on the delivery date now this is then total sales based on the delivery all right now let's see if the

**7:04** · results are different let me just get rid of that slicer and let me also take out the total discount and instead of having here a breakdown by product subcategory I want to have a breakdown by year and quarter so I'm going to take the product subcategory out and I'm going to add over here new breakdown by year and quarter okay now I want to have

**7:27** · the total sales on the right so let's track that down perfect now let's then add our new measure total sales delivery right next to the other total sales now you see the results are clearly different so they are close to one another however sometimes you will have products that were ordered in one quarter but delivered in the other and therefore there are small differences between total sales based on the aate and total sales based on the delivery date okay now if I want to do the same

**7:56** · thing for the discount well I have to write another measure or if I want to be able to switch dynamically well I would have to make use of field parameters now instead of all that we're going to make use of calculation groups again now the pattern will be similar to The Measure that I wrote okay so over here I'm just going to copy that and then we go back to the modeling View and then over here we can add a new calculation group all right then for the calculation item let's just base in what I just copied all right and let's rename it to

**8:28** · delivery date and then over here instead of hardcoding total sales we can again use this selected measure function which Returns the value of the measure to which you apply it and then it uses the

**8:43** · relationship based on the delivery date all right and then we just have to do it one more time so let's add another calculation item but now where we activate it on the basis of the order date so let's go over here new calculation item and this one is going to be for the order date and also here

**9:01** · we have to refer to the order date column and then let's also rename this calculation group just double click on it this is then the calculation group for the relationships and the calculation group column name let's just call this one active all right good so

**9:18** · we have the calculation group called relationships the column is called active and that holds the calculation items delivery date and Order date now let's go back to the report View and over here I want to have only the total sales so I'm going to take total sales delivery out and as we have seen before

**9:37** · we can use a slicer to activate the calculation items and apply them to our total sales measure so I'm going to add a slicer right next to it and then over here we can go to the relationships calculation group grab the active column and then we have our two calculation items delivery date and Order date now if I click here on order date nothing happens because the active relationship is already on order date in a model

**10:03** · however if I switch over here to the delivery date and now you see all of the total sales values based on active relationship between Tim date and F sales that is on the delivery date not on the order date okay and if we want to do the same for total discount or Total return amount well it works in the same way we can just drag in these measures total discount Total return amount let me just make this a little bit wider

**10:28** · okay and you will see that if I switch over here from delivery date to order date you see those measures also change because also here the active relationship is on whatever I selected in that slicer the Dex pattern gets

**10:45** · applied to any measure so now it's time for example number three we can also use calculation groups to make our life a bit easier when it comes to conditional formatting let's say we want to highlight all of the total sales that are above the average or the max maximum and the minimum then we could write a measure now let me show you the measure first and then how it becomes a bit easier when we use calculation groups all right so I'm going to take again this slicer away and let's also get rid of total discount and the return amount

### Example 3

**11:14** · okay now I want to have a measure that highlights the maximum minimum so I go over here create a new measure now let me just copy over the Dax pattern that we need we need to figure out what is the overall maximum value at the year quot level the same for the minimum value now how do you do that with a Max X and a minx where you iterate over

**11:35** · table that only contains the year and the quarters calculates the total sales at that level of detail and then Returns the maximum of those values now the same for the men and then with those values we can say okay check the total sales for that quarter is it equal to the max or the Min if it's equal to the max then we turn green otherwise we return Red

**11:54** · now and because we have variables we need to say return the last variable over there all right now I'm going to add it right next to the total sales so that you see how it works and there you go here we have green for the highest value and R for the lowest value now of course we don't just want to show the text we actually want to use it for conditional formatting so let me just take it out again go here to formatting

**12:17** · cell elements and then over here we can say to which field we want to apply the conditional formatting total sales background color FX and here we can make use of the field value of where we can then look for our measure all right now and there you go we have green and we have red and what if we want to do all of this again for the total discount or for the forecast well then we have to again write that long measure and adjust it for these new measures or we make use of calculation

**12:48** · rules so let's go for that option and see it in action now of course the pattern is going to be similar and now we go back over here to the modeling view where we were before four and we can again create a new calculation group and here we just paste that pattern from before now instead of total sales we need to have the selected measure so select total sales control shift L and then just write selected

**13:13** · measure all right now there's another thing that we need to update and that is what we want to return there at the end because this whole taex pattern will not only be applied when we use total sales in the conditional formatting but also when we show the actual values and then instead of actual values it will show green and red which is not what we want so we're going to make use of a dummy measure a dummy measure that also will

**13:38** · return total sales but has CF in its name and that one we going to use for conditional formatting now it will become clear as we do it so let me just say if all right now here we want to check if the selected measure name has CF in its name so we can do this with contains string here we have the selected measure name that we want to check and what we want to check for is CF all right now if it has then we want

**14:07** · to return green or red right just like before and otherwise it's just the selected measure value right so that means it is the normal normal total sales that shows in the table now another thing that we need to adjust is over here instead of green and red I'm going to return a one when it's either the max or the Min value and instead of returning over here blank I want to

**14:32** · return the selected measure value okay so we have a pattern now how can we use it for conditional formatting well let's go back and here we need to add that dummy measure that I was talking about so new measure now this is going to be the conditional formatting measure for total sales so let's name this one total sales what is important is that it has a CF in its name now can put it at the end or at the beginning and then over here we just refer to total sales all right now let's

**15:01** · go to our table then choose your formatting options then we go to sell elements background color for total sales now over here instead of field value we can go for a rule and then we can look for a measure that we just wrote C youf total sales and if this one is now equal to one that means it's maximum or minimum now of course you can also make it more flexible with maybe a one for the Max and a two for the Min however you like but for now I just go for one color and then I want to have

**15:31** · now choose the color that you like now over here I'm going to go for orange perfect and click okay now nothing happens just yet because we didn't apply that calculation item just yet right so let's go over here add again a slicer next to our table then we go over here to that new calculation Group which I still need to rename but let's add it already and activate the calculation item you see the orange color gets applied perfect now of course we can

**15:59** · also add more rules to it so that we can switch between different rules all right now let's go back to our modeling view let's first rename the calculation group so that we call this one conditional formatting highlights and then maybe as the name for that column that contains the calculation items we can say this is

**16:20** · the rule column then here we have our first calculation item now I would like to add two more now let me just copy over the formas and the first one is going to highlight everything that's above the average so over here let me just paste it in and the third one let's add that one as well which is going to highlight everything that's below the average now you see for the last two it kind of works in a similar way however over here we calculate the average value

**16:50** · based on the selected measure to which it gets applied and over here a small adjustment to when this one gets returned because now we want to return one when it's below the average value now the logic here after the return statement stays the same we need a measure that has CF in its name which is basically just a dummy copy of the

**17:12** · measure to which you apply it okay now let's go back over here to our report view now you see we have now three options free calculation items and again click on the other ones and see it nicely highlights those that I want to focus on now what if we also want do the same for total discount well then we need to take total discount Right add it

**17:34** · also to the table now no conditional formatting has been applied just yet then we go over here and make a dumy measure which is just going to refer back to the original Total discount measure total discount and this is CF okay for

**17:50** · conditional formatting and we refer to the total discount measure I we just repeat the steps from before and so over here formatting sell elements then we need the total discount measure turn the background color on FX and we can again

**18:06** · set up a rule now on the basis of that CF total discount which equal to1 all right and then I also want to have it in Orange click okay and you see that all of the Dex patterns that we set up with the calculation items also get applied now to the total discount field

**18:26** · perfect so you see that can save you a lot of time writing all of these conditional formatting measures now one thing to keep in mind though is that when we set up these calculation items now let me just open one of them then over here we are basing that maximum and minimum value on the year and quarter so that means it can only be used for a visual that uses that level of detail if

**18:49** · you have let's say a different visual where you want to highlight the maximum minimum that has a different breakdown like product subcategory done well you would need to have a separate calculation item for that one where you adjust it to product subcategory okay so

**19:05** · it would be nice if this could also be dynamic but I think there's no way to achieve that or maybe you have an idea then let me know in the comment section below all right that's it these are my three use cases of calculation groups that are a little bit less known however can be super helpful did you know all of them let me know in the comment section below if you want to start the year by boosting your powerbi scales then check out my upcoming powerbi design transformation program which starts in February it's already the third cohart

### End

**19:34** · where we have 28 hours of live sessions where we build reports together and I teach you all of my tips and tricks and everything about how to design a good functional report in powerbi so make sure to check it out if you want to dive a little bit deeper into calculation groups then check out these two videos over here where I walk you through some more examples thank you for watching I see you in the next video