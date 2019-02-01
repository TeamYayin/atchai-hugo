---
date: "2016-09-02"
published: true
title: "How to run a successful chatbot development project"
author: JohnGriffin
header_image: "/images/blog-healthcare-chatbots-user.jpg"
header_image_attribution: "Coffee photo created by freepik - www.freepik.com"
header_image_attribution_link: "https://www.freepik.com/free-photos-vectors/coffee"
---


In this article we’ll share a few things we’ve learned from building chatbots and conversational UI products.

We’ll cover how to select the right messaging platforms, the importance of conversation design and why we’ve built our own platform for the rapid development of chatbot products.


## What does success look like?

Before starting any project, it’s important to define goals and how you're going to
measure success.

One of the unique things about chatbot products is that you can sometimes **fake it
til you make it**. Why not pretend to be your bot for a while and learn about
your users’ expectations? Hey, if it’s good enough for Facebook M...


## Discovery

We use an [Agile development process that’s simple and
flexible](/about-us/how-we-work/). In order to hit the ground running there are a few
things we need to figure out first.

#### Choosing the right messaging platform

Ultimately the choice should be driven by your audience. Perhaps you've already got a
website or an app that you'd like to add a chatbot to?  One of the key reasons
people are building bots is “app fatigue”. The stat everyone throws around is
“the average American installs zero new apps per month” — it’s [not quite
true](https://www.tune.com/blog/no-the-average-american-does-not-download-0-apps-each-month/),
but the point remains: **We need to meet customers where they already are**.
What is your audience’s favourite messaging app?

![popular messaging apps](/images/blog-chatbot-popularapps.png)

> Most popular messaging apps per country (Feb 2018)

We’ve produced an extensive [review of messaging app platforms that are suitable
for
chatbots](/blog/2016-08-11-whos-winning-the-messenger-app-wars/),
which is good background reading. Make this decision based on hard evidence if
you can, rather than trying to match up the demographics of your audience and
the apps. In the same way that you would review Google Analytics before
rebuilding a website in order to know which browsers and devices you need to
support, you should aim to collect data from your audience on which messaging
apps they use.

Facebook Messenger is by far the most popular option, with over 1 billion monthly
active users and strong support from Facebook to grow the platform.  We'd recommend
looking at Messenger first unless you have particular anonymity requirements or you
need to support basic devices that only use SMS.  


![SMS and Facebook Messenger Bot development](/images/blog-chatbot-project-sms-fb.png)

> Interactions can be delivered differently for SMS and Facebook Messenger bots

#### Capturing Requirements

We like to capture requirements as user stories, since they force us all to
think from the end user’s perspective and help us to prioritise the requirement.
A user story always has the same format:

*As a &lt;user role&gt;, I want &lt;requirement&gt;, so that &lt;reason&gt;*

For example, if we were designing the classic pizza-bot we might identify the
following requirement:

*As a previous customer, I want pizzabot to remember which toppings I dislike,
so that I don’t receive inappropriate recommendations.*

#### User Journeys and Conversation Design

The next step is to prioritise our user stories, take the most important ones
and figure them out in more detail. This is where we start getting into
designing the conversation at a high level.

Before we consider the bot’s personality, we must design conversation flows that
optimise the process for our customers. This could be seen as the equivalent of
user journey mapping and wireframes for visual UI projects.

![Designing conversational UI](https://cdn-images-1.medium.com/max/800/1*nBDZFIqwRXS8oAePBXyYhg.png)

#### Tone of Voice

Before we start writing final copy we need to develop a shared understanding of
the bot’s personality and tone of voice.

There are several techniques to achieving this but the simplest is to develop
the character of the bot as if it was a complete person who is just doing their
day job by answering the user’s queries. This results in a bot character story
that explains who they are, their motivations and quirks.

Developing a fully fledged character is the key to writing a script that doesn’t
grate after multiple uses. It also helps you see when humour is an effective
tool and when it’s an annoying distraction.

## Iterative Delivery

#### Process

We aim to deliver a working product, deployed and ready to use by real users,
right from the very first sprint. The idea is to then iterate on this product,
adding more features until we meet the goals we set out right at the
beginning.

It’s important that we test the product with real users throughout the process.
There is no better way to understand whether we’re building the right thing.

#### Conversation Design

Bot scripts are written incrementally, starting with the core functionality and
then expanding into personality driven intents and multiple responses as the
project develops.

Conversation design also involves training the natural language processing to
understand your users, again focussing on the core terms for the key
functionality at the start and then expanding as user data becomes available.

The process of matching user intents to existing features or highlighting the
need for new responses is a continuous cycle that moves the bot from a decision
tree structure to a natural conversation over several sprints.

#### Technology

We’re constantly improving our technology offering, and we’ve invested in
developing a core platform that benefits all our customers. Out of the box we
can offer:

* Connectors for major messenger apps (e.g. Facebook Messenger) and SMS.
* A powerful engine that allows for complex conversation workflows.
* Human in the loop UI — override the bot and talk directly to your users.
* Integration with advanced NLP products like wit.ai.
* Push content to users from your legacy CMS platform via RSS feed
* RESTful API for quick integration with any other product.
* Fully managed solution that we can host and support for you.

Typically you will find that your users are spread over multiple platforms, so
we allow you to handle this transparently, providing you with a single interface
to all your users regardless of the messaging app they’re using.

![Real-time messaging bot UI](https://cdn-images-1.medium.com/max/800/1*Xmz9RtGH7Y5w-WlfaqP_EA.gif)

> Real-time cross-platform messaging UI, allowing you to interact with your users.

#### Analytics

Once your bot is out there in the wild, you will want to keep learning from your
users’ behaviour. We will set up analytics tools so that we can all monitor the
performance and make informed decisions to continually improve the product.

<img src="/images/lastseen-engagement.png" style="width:100%">


## How much does it cost?

Good question! We’ll give you a simple answer…

It can cost as little as £25k for an MVP — that’s a one week discovery
phase and two sprints to get a working product out there. We can deliver
this cheaply and reliably because of the technology we’ve already built, allowing us to focus our time
on designing an experience around your users and brand.

Of course the full answer is that it depends on how complex the product is that you
want to create. If you want to integrate with other technology, or use
sophisticated NLP / AI techniques then it can take many sprints to train
learning algorithms to be effective and meet product goals.

We've built successful chatbot products for clients as diverse as the UK Department of International Trade,
Asthma UK, Danone, and the South African Broadcasting Corporation (SABC).

We’d love to help you realise your vision.  You can [drop us a quick note](mailto:john@atchai.com) to set up a call.
