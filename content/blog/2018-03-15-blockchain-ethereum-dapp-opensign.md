---
author: JohnGriffin
date: "2018-03-15"
published: true
title: "OpenSign - Decentralized Agreements on the Blockchain"
header_image: "/images/blog-header-generic.png"
---

OpenSign is a free, decentralized alternative to products like DocuSign and EchoSign.  It allows you to make agreements without requiring any trusted third party to keep track of your documents and signatures.

**td;dr** The OpenSign dapp is currently an MVP, you can <a href="https://opensignapp.com">try it yourself now</a> if you have some Ethereum and your browser has MetaMask installed.  


### How does it work

We've tried to make the process of creating multi-party agreements as simple as possible, but you will need some experience of using Ethereum and Metamask for any of this to make sense.  If you don't have that experience yet then I recommend reading <a href="https://cryptocurrencyfacts.com/metamask-explained/">this guide</a> first.

When you come to the OpenSign Dapp you will be led through a simple three step process to create an agreements:

![OpenSign screenshot](/images/opensign-screenshot.png)


#### Step 1: Upload a document
Upload the document or contract that you wish to be signed. It will be stored on IPFS, a public decentralized filesystem.

#### Step 2: Sign the document
Clicking "I agree" should open MetaMask and request you to submit a transaction for zero ether. There will be a gas fee for this transaction, likely between $0.3 and $0.30. Your ethereum address will then be publically associated with the document in our smart contract.

#### Step 3: Invite others to sign the document
You will be given a URL that you can share with other people. This URL will allow them to add their signature to the document too. You can use this URL yourself to see which ethereum addresses have added their signature.


At this point you can email the URL to the other parties that you wish to sign the document.  It's likely that a feature to send out emails will be added to OpenSign later.

### Technically how does it work?

The source code is <a href="https://github.com/atchai/opensign">available on Github</a>

The site at opensignapp.com is hosted on Amazon S3 & Cloudfront but it is also available <a href="https://gateway.ipfs.io/ipfs/QmUu7kuy7dHCC5RDL3hscji81Fb6EmoBRzmwcrgJweRVjJ/">on IPFS</a> for decentralization maximalists.  

![OpenSign stack](/images/opensign-stack.png)

The website was built using the embark framework, which includes the popular web3 library.  When the page is first loaded in the browser we do a number of checks to figure out whether the user has metamask installed, if so whether they're logged in, and if whether they are on the right network.  At the moment we are only supporting the Ropsten test network. 

When a user takes the action of signing a document, we use the web3 object that has been injected by metamask to request that a transaction be signed by the user.  This transaction will call either the addDocument or signDocument function in our smart contract.  

The smart contract is written in solidity:

<script src="https://gist.github.com/johngriffin/c0c0c4a180702f02e9625a7d1ef63239.js"></script>

We create an unique "agreement_id" to act as the primary key out by hashing the ipfs file hash along with the current timestamp.  We can't just use the ipfs file hash as this will be the same if the uploaded file is the same.  It's likely that two different agreements might want to use the same document.

We'll be writing a lot more about how to write secure and optimised solidity code soon.



### Why is decentralisation important
If you are asking this question then you are presumably looking for reasons more practical than ideological.  These are probably the most important ones:

* Cost - You don't have to pay a monthly subscription to a service to keep track of your agreements - just pay a small transaction fee when signing.
* Risk - You don't have to depend on a third party (e.g. DocuSign) to still be around when you need to check up on a contract that was signed.  


### Future Work
There's a lot of improvements that can be made to this basic service.  It's important to note that the product is only an MVP at the moment.  We'd love to hear from anyone who's interested in collaborating on further development of OpenSign, the features that are most important to look at are:

* Improve UX - e.g. send out emails for the user to invite other parties to sign.
* Privacy - support encryption of the uploaded documents
* Identity - support some identity protocol such as Civic.
* Security - audit the smart contracts and js code.


