---
author: JohnGriffin
date: "2018-08-30"
published: true
title: "Can we save the utility token?"
header_image: ""
---

## Introducing a dynamic bonding curve token model

Utility tokens have received a lot of bad press recently, and for good reason. Many ICOs that sold utility tokens seem to have massively over-estimated the supply of tokens required for normal usage of their networks. The price of these tokens has been supported by speculative investors who presumably didn’t give much thought to the fact that they were not designed to function as a store of value and will likely be sold in return for usage as soon as they’re purchased by legitimate users, resulting in what is now commonly referred to as [the velocity problem](https://www.coindesk.com/blockchain-token-velocity-problem/).

We argue that in spite of the bad maths and hangover from the hubris that has gone before, there is merit to the idea of the utility token and that we can find models that better reflect their true value, discourage speculation, and result in an asset that can be programmed to incentivise desirable dynamics within a community built around open source software.

We present a model that’s based on the idea of bonding curves, aiming to provide development teams with a way incentivise collaboration and sell early access, for those early adopters to benefit from the growth phase, and for later stage users to benefit from a predictable and stable price.

The specific model presented here as an example has been adopted by our partner [Mythril](https://mythril.ai/) — a [ConsenSys Diligence](https://consensys.net/diligence/) project building a [security tools platform](https://media.consensys.net/mythril-platform-api-upping-the-smart-contract-security-game-eee1d2642488) that brings advanced security analysis directly into smart contract development environments.

### A Multi-Phase Bonding Curve Design

One of the key innovations in the token model we’ve created for Mythril is the concept of a multi-phase, or piecewise bonding curve. If you’re not already familiar with the concept of bonding curves then you should check out [this article for a thorough explanation](https://medium.com/@justingoro/token-bonding-curves-explained-7a9332198e0e):

Essentially the “traditional” bonding curve is a relationship between token supply and price, often a quadratic, most famously implemented in the [Bancor protocol](https://www.bancor.network/). The typical bonding curve looks something like this:

![](https://cdn-images-1.medium.com/max/1600/1*L7RH1JaFDjJ2inkPE9z8LA.png)

> A “traditional” bonding curve

On the x-axis we have token **supply**, and on the y-axis token **price**. A smart contract can act as a market maker by buying and selling tokens according to this formula, in exchange for a reserve currency, e.g. ETH. Tokens are minted when they are sold, and burned when they are bought.

This is a powerful idea that means anyone can launch a token with a transparent relationship to an underlying reserve currency and instant liquidity without depending on a third party exchange. The token can be bought and sold by a smart contract at any time for a predictable price. However there is some interesting [research using multi-agent reinforcement learning](https://medium.com/incentivai/bonding-curve-simulation-using-incentivai-2b2bfe0c6400) that suggests the most commonly implemented quadratic curve or “Bancor formula” may lead to price volatility due to speculation, especially when token distribution is uneven.

#### So let’s make our own curve

Ultimately we could make the relationship between supply and price whatever we want it to be with the only practical limitation being the gas cost of on-chain computation of price.

Taking the Mythril token model as an example, the curve resembles a sigmoid function but there are three discrete phases where the formula relating supply with price differ for each. One benefit of this approach over using a single function is that we could externally trigger phase transitions, or use time, or some calculated metric . We could do something like increase the gradient as buying pressure cools off in the early adopters phase. We could even redefine the price curve of a later phase before it has been reached.

![](https://cdn-images-1.medium.com/max/1600/1*NdDJEh4K-ELQ4mnWtC4Nvw.png)

> A multi-phase relationship between price and supply

1.  **The pre-release phase** where a number of tokens are purchased by the founding team for a low, constant price prior to launch. The majority of these tokens are locked up in vesting contracts and the rest are distributed to funders and used as incentives for partners and the community.
2.  **The early adopter phase** where price increases linearly with supply — the aim being to reward early adopters by enabling them to purchase their usage at a discount and to incentivise them to signal their intent early. In order to combat speculative behaviour in this phase we are whitelisting participants who have expressed an interest in the project and limiting the number of tokens that can be purchased per individual and per partner.
3.  **The production phase** is when the token becomes available to the general public. The curve flattens out but still has a linear relationship up to a point where it becomes a constant. We want the price to be relatively stable and to reflect primarily the usage of the service. Therefore, we use a low gradient combined with other measures to disincentivize speculation. This approach also allows for a certain amount of price discovery and allows the founders to sell back their tokens to the market, but only if usage is genuinely increasing as their selling will be reducing supply and therefore reducing the price they will receive per token.

#### What about the velocity problem?

The velocity problem refers to the fact that most tokens do not function as a store of value and therefore there is little reason to hold them any longer than necessary. This results in the tokens having a high velocity of transactions and hence, using the MV = PQ valuation methodology, the token value will be low. While it’s quite possible that this isn’t the correct way to value your particular token, and the [relationship between utility and store of value](https://medium.com/@QwQiao/the-false-dichotomy-of-utility-and-store-of-value-27fe12bf3bdb) certainly isn’t binary, let’s address this issue head on:

If we want to reduce velocity we have to provide benefits to users that lock their tokens up for a longer period of time. If you have for example 5000 daily active users who each spend 1 token per day then you only really need 5000 tokens. However if you have an annual plan priced at 250 tokens per year, those same 5000 users may require a total token supply of 1.25M tokens.

Introducing staking for enterprise customers and partners, potentially to give them some governance rights or to unlock a priority level of SLA can make a bigger impact, e.g 100 users staking 20,000 tokens each requires an additional 2M tokens.

Ultimately it’s essential to design these mechanisms up front and have an understanding of how tokens are likely to be used by non-speculative users of your system in order to design a suitable price curve.

### Tokenised SaaS Licensing

The main focus of this article is the token model as described above but to put the token model in context and give you a taste of what we’re developing, here is how the system works in practice for end users who want to buy access to the Mythril platform API.

The tokenized license system works by separating the purchasing of a plan into two steps. In order to optimise UX, these steps can be combined into a single transaction and the user will be presented with a familiar “choose a plan” page and checkout process.

![](https://cdn-images-1.medium.com/max/1600/1*6_4OVLtjrS0V2CW_bWyiZg.png)

> Diagram showing flow of tokens in the Mythril license system

The first step is to purchase MYTH tokens from a market contract. The market mints tokens when they are bought, and burns them when they are sold. The effective price for each order is calculated based on the custom bonding curve as described above.

The second step is to exchange these tokens for a license by depositing them into the license contract. The first plan on offer will be a daily “pay as you go” plan. When the user makes an API call, the API will check with the license contract to ensure that the user has an active plan. If the daily plan is priced at, say, one token per day, for every day where at least one API call is made, one token is deducted from the user’s balance. The user can then make as many API calls as they want within that day and they will not be charged for days where they don’t make any API calls.

If the user decides that they won’t need to use the API for a while they can simply withdraw their unused tokens and either transfer them to other users or sell them back to the market. Tokens that have been used remain in the license contract and will be distributed accordingly between contributors, tool developers and the Mythril team, who can in turn choose to sell them back to the market.

#### **Benefits for end users:**

*   Pay-per-use: We are enabling a true utility based model; where tokens are deducted for actual use only. Unused tokens can be sold back to the market at any time.
*   Transferability: Subscriptions are divisible and can be shared and transferred between users simply by sending tokens, this gifting dynamic could act as a driver for viral growth.
*   Passwordless login: Users are identified by the pair API key and can be authenticated using the Ethereum private key. Users do not necessarily have to enter personal information.

#### **Benefits for developers and community :**

*   Revenues generated by tool users can be split easily and transparently in a decentralized fashion between contributors and the founding team. Note that simply holding the token provides no right to dividends, and so for regulatory purposes should not be seen as a security.
*   Transparent dynamic pricing based on demand can be implemented, leading to more efficient price discovery.
*   It is possible to pre-mint a number of tokens that can be distributed to incentivise and reward contributions to the project, who can sell them back to the market as supply increases proportionally to usage and token price.

### Future Work

We are working on a ushering in an era of **open services**, an evolution of the open source movement.

If you’d like to talk about how we might work together, please [get in touch](mailto:john@atchai.com)
