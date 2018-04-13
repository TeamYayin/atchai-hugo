---
date: "2017-08-29"
published: true
title: "Eyewitness Platform sprint 1 update"
author: TomHewitson
header_image: "/images/blog-header-generic.png"
---

The Eyewitness platform is an open source messaging bot and management interface designed to let news organisations distribute stories and collects User Generated Content (UGC).

*The project is funded by [Code for Africa](https://codeforafrica.org) and [Bill and Melinda Gates Foundation](https://www.gatesfoundation.org/).*

![](/images/blog-eyewitness1-whiteboard.png)

### Funding issues

First off, an apology. When we pitched this project we intended to begin
development sometime in spring and to have a working product out in the market
by this point.

Unfortunately, the funding process meant Code for Africa weren’t able to provide
all the money needed to complete this project and we didn’t want to risk
delivering a product that wouldn’t adequately meet user needs.

This has meant the last few months have been spent attempting to secure the
additional funding needed to make the Eyewitness platform a reality.

I’m happy to report that, thanks to the hard work of Justin from Code for
Africa, Facebook itself has decided to provide the additional funding required
and we’re now in a position to start building the platform.

Also, although development has been on hold we’ve made good progress on the
designs with the help of our partner news organisations
[SABC](http://www.sabc.co.za/), [Punch](http://punchng.com/) and [The
Star](http://www.the-star.co.ke/) so we should be able to move quite quickly
from now on.

### User needs + user journey mapping

We conducted several sessions with the partner organisations to find out their
need for the product we’re proposing and have made several changes to our
proposal based on their feedback and previous projects they’ve run.

Although collecting UGC was the initial focus of the Eyewitness platform it
quickly became clear the news organisations have previously trialled various
apps and websites that do this with limited success.

Instead they highlighted a need to let users subscribe to their content in a
more deterministic way than Facebook newsfeed allows.

We also realised that we have to give users a reason to use the bot before we
can use it to ask for UGC. We’ve therefore decided to make the primary consumer
experience about subscribing to a feed of the news orgs stories and submitting
UGC as a secondary feature.

Based on the news orgs experience with previous projects we decided it was
essential we launched as early as possible so we could get real data on what
will work.

We’ve therefore stripped back the proposal to three core features that we’re
launching as a minimum viable product in the next few weeks:

#### > Provide an RSS feed of the news orgs stories via messenger

#### > Let users submit stories via a webform linked in the permanent menu

#### > Send breaking news alerts that trigger notifications on the phone

<br>

You can see the updated user journey reflecting this below:

![](/images/blog-eyewitness1-flow.png)

As part of my design process I like to prototype most interactions as it makes
it much easier for others including stakeholders and developers to provide
specific, actionable feedback in a way that’s really hard with a flow chart.

Prototyping is supposed to be rough and dirty so I’ll often use other web
services etc that demonstrate what I mean (for example the Google form in this
one) rather than spend half a day creating an asset that will only be used for
one sprint.

When I’m designing Facebook Messenger bots I tend to do my prototyping in
[Chatfuel](https://chatfuel.com/) which is lightning fast to build simple
interactions in but you’d have to be braver than me to use it in a production
environment!

You can see the MVP prototype here:

{{< youtube 5ptwbMGJMqo >}}

Design is, without doubt, an iterative process and I’m sure that this design
will change quite a lot once we’ve got some real data on how users are
interacting with it. The key is to get to that point as quickly as possible.

If you have any feedback on how we could improve this interaction I’d love to
hear from you.

### Up next

John and the team at Atchai will be developing and deploying the MVP with the
help of Isabelle who has joined us to support the news org partners in
implementing the platform and conduct research with end users once the product
is live.

In the meantime I’m going to be looking at:

#### > how often the news orgs use the ‘breaking news’ alert functionality and start thinking about a management interface for it

#### > how much UGC is submitted to the news org and how it should be presented to the journalists

#### > whether UGC should be submitted via a form or within the conversation flow
(there are benefits to both)
