---
title: 'Apart of the Pack &#8211; Email Communication Before and After the Game'
layout: single

---
#### Pregame Warm-Up {#pregamewarmup}

When you buy a ticket to see a sporting event, you receive an email receipt with the typical ordering information and your seat location. Your receipt gets scanned as you walk into the game and enjoy your outing.

Ticketmaster is our primary ticketing system. Here are the emails you receive, with an example receipt.

![Ticketmaster Receipt](http://i.imgur.com/nW0LdLo.png)
  
![Ticketmaster Ticket](http://i.imgur.com/7Osb5mB.png)

We had a few goals for improving the communication before and after the game for our single game ticket purchasers. What if it was your first time at the Target Center? Maybe you are visiting from out of town? Maybe you want to know exactly where you are sitting.

We wanted to address these issues to improve the experience of the fan before coming into the building. The perfect way we though to do that is with an email communication.

Here is a look at the Pregame Email: 
  
![Pregame](http://i.imgur.com/AuS6hzc.png)
  
![Pregame2](http://i.imgur.com/mcFrBhq.png)

[Litmus](https://litmus.com/pub/2d89496)

In the Pregame email, we include information about the game date, time and opponent. If there is any special information about the game, I try to include that as well. We also take the chance to use the email for market upcoming games. 

For people joining us for the first time, we include parking instructions and a link to the Timberwolves Seat Viewer. This allows consumers to easily find where they need to go when traveling to the Target Center.

Here is a look at our Postgame Email:

![Postgame](http://i.imgur.com/k1xTK2T.png)

[Litmus](https://litmus.com/pub/7276b33)

At the beginning of the process, we were sending game recaps to help drive users back to our webpage. We also included a survey to gather feedback from our fans. We can then use feedback to improve the Timberwolves experience.

#### The Set-up {#thesetup}

![Script Workflow](http://i.imgur.com/rXkD25l.jpg)

When we were using Eloqua as our ESP, We used SQL exports and Scribe to import the lead data to automate the program. In early October, We migrated to Marketo. 

Scribe has a connector to integrate data with Marketo but it was only available with Scribes cloud platform. This wouldn&#8217;t be an option for us here. I did some noodling with the Marketo API and I found a great API Wrapper from the folks at [Segment.io](https://github.com/segmentio/marketo-python) that laid the groundwork for the automation.

We created a SQL script to export our single game purchasers into a \*.csv. The python script would then download the \*.csv and use Marketo API calls to check if the customer is in Marketo. 

(Another SQL script runs behind the scenes that adds single game purchasers to our CRM Database (MS CRM Dynamics 2011) which syncs with Marketo)

If the contact is in Marketo, the script adds the customer to the specific game campaign to receive their emails.

#### How did we do? {#howdidwedo}

![Email Stats](http://i.imgur.com/Cp4lv5a.png)
  
![Link Stats](http://i.imgur.com/6oruuRJ.png)

There was a discrepancy between the number of people that bought Single Game Tickets and the number of people that eventually received the email. This could have occurred from a number of reasons.

_Bought from a Third Party Vendor_

We would only get data if someone purchased via WolveTix (Ticketmaster) or NBAMarketplace.com. 

_Not a valid email address_

Maybe they picked up tickets at Will Call.

_Our SQL script is wack_

We might not have accounted for errors in our SQL script.

For those that did recieve an email, It seems the response was positive. Over 50% of people opened the pregame email and 44% people opening the postgame email. Our top links were the Seat Viewer and Parking Instructions for the Target Center. People were engaged with our surveys with over 200 responses.

#### Chalk Talk &#8211; Improvements for the Future {#chalktalkimprovementsforthefuture}

_Move useful information higher in the email._

The seat viewer and directions for parking are the top things our fans want according to our previous stats. Maybe we can even link them directly to their seats with their purchase data.

_Make sure we are reaching EVERY fan_

These emails make sense for fans that don&#8217;t get to the arena often. Maybe we can educate more fans about the Arena and local businesses in the area. It could be a great way to incorproate corporate sponsors as well.

_Continue to improve the Marketo API Script_

I need to get a better understanding of Archtics and the way data is imported into CRM. The Marketo error log has over 500 failed campaign additions. These issues need to be addressed before the WNBA season.