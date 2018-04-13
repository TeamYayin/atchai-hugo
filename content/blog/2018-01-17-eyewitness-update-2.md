---
date: "2018-01-17"
published: true
title: "Eyewitness Platform sprint 2 update"
author: IsabelleBrown
header_image: "/images/blog-header-generic.png"
---

The Eyewitness platform is an open source messaging bot and management interface designed to let news organisations distribute stories and collects User Generated Content (UGC).

*The project is funded by [Code for Africa](https://codeforafrica.org) and [Bill and Melinda Gates Foundation](https://www.gatesfoundation.org/).*

![Facebook Messenger bots launched for The Star and Battabox](/images/blog-eyewitness2-bots.jpg)

### Feedback on our first release
As detailed in the update for release 1, our first version of the Eyewitness chatbot focussed on providing a reason for people to connect with the bot. When we launched the first release of the chatbot for our pilot partners [The Star (Kenya)](http://www.the-star.co.ke/), [SABC (South Africa)](http://www.sabc.co.za/), and [Battabox (Nigeria)](https://www.facebook.com/battabox), the bot’s primary feature was to serve the latest news stories pulled in from their RSS feeds, with the ability to click through to the website where the stories were hosted. Submitting your own story or tip off was made available via a link to a webform in a permanent menu item, with submissions directed to our partners’ news desks.


Whilst partners appreciated the ability to generate more views on their content, they found the fact that the bot had entirely ‘taken over’ the handling of interactions with their users problematic. Because we didn’t want to invest too heavily in promotion at this early stage, most users were accessing the bot by clicking ‘Message’ on the partner’s Facebook page, expecting, as before, to be able to speak to a real person. Partners could see users struggling to understand that they were interacting with a bot, but had no way of switching the bot ‘off’ when they wanted to step in and talk to a user.

It’s worth highlighting this user experience problem, because it’s an important illustration of the reality of introducing new technologies to emerging markets. It’s frustrating enough having an unsatisfactory conversation with something you know is a chatbot, but downright aggrieving if you don’t understand the concept of a chatbot in the first place. Our first iteration request was therefore to enable page managers to switch the bot on and off when needed, and we also realised we needed to pay close attention to the way first time users were onboarded by rethinking their user journey more carefully.

Partners also suggested that users should be able to sign up not only for breaking news updates delivered via Messenger, but also to search the stories by topic of interest. Because of the reality of connectivity and data costs in the countries we launched in, many users habitually go offline for a few days. Being able to quickly catch up on the news topics you’re most interested in seems like an interesting idea that we’d like to explore further, but didn’t seem a priority for our second release.


### The second release

To address our partners’ concern that they could no longer talk directly to their users through Facebook Messenger, we needed to create a user interface and a system of toggling the bot on and off.  If they had used the Facebook page UI to send messages manually to users, the bot would still be active and would interrupt the conversation when a message was received!

Creating our own UI allows us to provide a way to “take over” from the bot, have a conversation human to human, and then switch the bot back on.  The UI we’re building also provides a number of other features, including:

#### > View all conversation history with users
#### > Step into the conversation when needed by switching the bot on and off
#### > View all stories that have been published through the bot
#### > Adjust the bot’s welcome message, allowing for a greater personalisation of the user experience depending on the partner’s brand tone


<br>


One of the challenges we anticipated was the addition of a new interface to the roster of pages our partners use to manage their social media presence. Given that our aim is to make our partners’ lives easier, this puts us in a bit of a bind as their requirement to run a ‘flexible’ chatbot on their page is only possible with the creation of an additional interface. We are hopeful however that by continuing to add useful features to the dashboard to increase user engagement and optimise the handling and analysis of UGC, the Eyewitness product will add enough value to compensate for any inconvenience.

### What’s next

We went live with our second release too close to Christmas to gather detailed feedback from our partners, however we decided to proceed with planning for release 3 based on what we had learned already, and on the data we could now more easily visualise thanks to the new dashboard.

A quick analysis of the UGC sent in to our partners highlighted some recurring themes, such as:

* Responses to stories, including corrections
* Advertising enquiries
* Marketing/content proposals
* Stories
* Appeals for help
* General enquiries


![Dashboard designed for sprint 3](/images/blog-eyewitness2-dashboard.png)

We have noticed that almost all of these enquiries are going unanswered, causing a lot of frustration for the users trying to make contact.  On our third release we are therefore keen to see how we can use the chatbot to ‘triage’ users’ messages in a way that handles any recurring customer service style enquiries on behalf of the page, whilst pushing actual story leads to a more prominent position.  

We are also planning to give users a different conversation experience depending on where they are coming from. Users accessing via the Message button on the Facebook page would see a user experience which reflects their motivation to send a message, whereas users clicking through from other sources would be served with the news stories more quickly.

Additional small features include:

*  Provide a simple button to assign stories to breaking news via the dashboard (it seems like doing this on their RSS feeds was a challenge for our partners)
* Improve the conversation UI with features like timestamps and better sorting
* Performance enhancements to deal with the large number of messages in the UI
* Integrating basic free analytics to the dashboard

**Finally, we’re on the lookout for additional partners to try the bot for free, which will increase our understanding of how Eyewitness could support the work of news organisations across Africa. If you’re interested, get in touch with [isabelle@atchai.com](mailto:isabelle@atchai.com) for a demo and a chat!**
