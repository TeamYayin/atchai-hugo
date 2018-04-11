---
author: JohnGriffin
date: "2018-04-11"
published: true
title: "Software licences as non-fungible tokens"
header_image: "/images/blog-licensetoken-header.png"
---


What if all our software licenses were compatible and we could go to a single
integrated app store and sell say three days of Adobe Creative Cloud and buy two
days of Microsoft Office? This flexibility would be a clear win for consumers
but would surely lead to a loss of revenue for software vendors. Hmm, but what
if this easy transferability of licenses also reduced piracy?

In this post we present a simple proof of concept, representing software
licenses as ERC721 tokens on the Ethereum blockchain, and using Metamask to
passwordlessly log in to a web app by proving that you own the address that owns
the tokens. We’ll also discuss some of the potential pros and cons of taking
this approach.

<a href="http://licensetoken.atchai.com">
![Screenshot of licensetoken.atchai.com](/images/blog-licensetoken-top.png)
</a>

[Try the live demo on Ropsten testnet](http://licensetoken.atchai.com)

[The code is open source and on Github.](https://github.com/atchai/licensetoken)

Although the demo here focusses on web based SaaS software, the same principle
can be applied to desktop and mobile, where the wallet would be embedded in the
software.

## Potential benefits of this approach

### **Transferability**

This is obviously a benefit to the consumer, offering more flexibility. It is
also safer than the current methods of transferring a serial number or a
subscription membership, where you either take the risk of non-delivery or use a
third party escrow service like Ebay.

It’s not all bad for the vendor either, a token is a smart contract after all,
so you can program whatever rules you want to constrain how transfers happen.
For example you could set a time period where tokens are locked and
non-transferrable, or you could set up a revenue share where you get a
percentage of the secondary sale.

### **Anti-Piracy**

A particularly interesting property of making licenses transferrable and owned
by an Ethereum account is that you need to possess the private key in order to
authenticate yourself, and if you share that private key then you risk the token
being transferred away from you.

This is only really a deterrent for wide-scale sharing of the private key, and
probably wouldn’t stop you sharing the key with someone sitting next to you. It
would however deter you from posting it on a public forum.

### Privacy

Theoretically there’s no need to share anything other than your Ethereum address
to buy tokens and to authenticate.

Another interesting use case is where you want to prove that you have an active
subscription with a partner product. Normally the partners would have to share
some information about you, but in this case you just need to prove to the
partner that you own an address, as you normally would to authenticate, and they
can then look up your subscription.

This is essentially a single-sign-on (SSO) system.

## Technical Details

This diagram illustrates a successful authentication flow between the end user
(client), software vendor (server) and smart contract.

![](/images/blog-licensetoken-flow.png)

> Illustration of a successful purchase and authentication flow of License Token

While we are focussing on the case of web-based software here, the same
principle also applies to desktop and mobile software. The client’s private key
would be embedded in the desktop or mobile software rather than within a browser
or browser extension wallet like Metamask.

## Our implementation

In our proof of concept, all of this flow is initiated from a single web page.

<a href="http://licensetoken.atchai.com">
![Screenshot of licensetoken.atchai.com](/images/blog-licensetoken-steps.png)
</a>

The web page uses the [web3.js](https://github.com/ethereum/web3.js/) library to
communicate with [Metamask](https://metamask.io/) — other Ethereum enabled
browsers could be supported. Webpack is used to bundle the code.

The server is written in Node.js, making use of
[MetaAuth](http://://github.com/I-Gave/meta-auth) to verify the signature.
Incidentally the signature methods of Metamask are [subject to
change](https://medium.com/metamask/scaling-web3-with-signtypeddata-91d6efc8b290]),
hopefully this will stabilise soon so that these methods can be used safely in
production. We make use of the Infura API so that we don’t have to run our own
Ethereum node to check the contract state.

Our smart contract is managed with [Truffle](http://truffleframework.com/), and
we’re using the new [OpenZeppelin
ERC721](https://github.com/OpenZeppelin/zeppelin-solidity/tree/master/contracts/token/ERC721)
contract as a base.

<script src="https://gist.github.com/johngriffin/4cb1118ba0533ec918add9dff1745ddd.js"></script>

We did have problems trying to prototype this in
[Remix](http://remix.ethereum.org/), though all functions of the OpenZeppelin
ERC721Token contract seem to be implemented, Remix keeps throwing the error:
“This contract does not implement all functions and thus cannot be created.”

## Next Steps

There are lots of trivial improvements that can be made to the work we have
started here. This is only intended to be a proof of concept. While developing
this we discovered a few other people exploring this territory. Most notably
there’s a project that’s just been released called
[DotLicense](https://github.com/cryppadotta/dotta-license) — it’s more focussed
on desktop software licenses at the moment but it’s a full framework that uses
ERC721 tokens and though we haven’t tried it, it looks great!

When it comes to subscription billing there is no way for a smart contract to
reach into your wallet and extract a recurring amount each month. You would have
to pre-fund a contract with multiple terms up front, then you could potentially
withdraw / transfer at a later date. We envisage a system where all your
subscription licenses are managed in one place, so this single contract would
act like your bank account in the traditional direct debit / recurring credit
card payment scheme. There is some good discussion about standardising an
interface for this over in [EIP
948](https://github.com/ethereum/EIPs/issues/948)

It would be great to see a full web app built out that would allow software
vendors unfamiliar with Ethereum and Solidity to configure and deploy a license
contract. This would be something like Stripe’s admin interface, allowing you to
define plans and licenses, view payments and customers.

If we want to trade our licenses though we will need somewhere to do that. There
are already a few of marketplaces to trade ERC721 tokens (notably
[Rarebits.io](https://rarebits.io/) and [OpenSea](http://opensea.io)) but it’s
likely that we would need a specialised exchange for licenses and subscriptions.
There doesn’t seem to be any need to change the way software is currently
distributed — e.g. through websites and app stores.

Legal —some work needs to be done to ensure that buying the token commits you to
the terms of the license. This could be some sort of Ricardian contract.

Commercial — tokens make more immediate sense for software that is already using
a utility-based pricing model. For subscription-based pricing the benefits are
not quite so clear. A lot of thought and experimentation needs to go into
whether we can find models that increase flexibility for the customer without
cannibalising revenues for the vendor. The hypothesis to take forward here seems
to be similar to Spotify’s, by improving the UX and making it easier to purchase
small amounts of software you’re more likely to pay for it than to steal it. Can
the growth in participation in legal purchase outweigh the revenues lost from
people churning out of unwanted subscriptions?

There are lots of creative ways we can manipulate this calculus to make it work,
revenue shares of secondary sales, limits on transferability, partnership and
affiliate deals, cross vendor bundling. All of which can be implemented as rules
in the license’s smart contract.

It’s unlikely we’ll see any degree of adoption outside of a few crypto software
projects unless we work through the above issues successfully. If we can come up
with good solutions then the vision presented at the top could become a reality!
