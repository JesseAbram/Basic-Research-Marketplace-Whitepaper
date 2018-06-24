BRM Whitepaper 

Intro

Ever since the days of Timothy May and the cypherpunk movement the dreams of a decentralized marketplace have lived in the minds of many. The dream was a place where people can anonymously buy and sell anything. Since then, many building blocks for the vision have been created. 

It is fitting that the cypherpunk movement was where this started as the biggest piece of the puzzle today came from another cypherpunk Satoshi Nakamoto. In 2008, Satoshi wrote the whitepaper and coded a form of online money known as bitcoin. 

One of the main appeals of bitcoin was that it used a peer-to-peer network to create a monetary system. The question is: if this was a building block to this decentralized market place being brainstormed in the 90s, then why did this take so long especially when we had peer-to-peer networks already like BitTorrent?

BitTorrent worked by sharing files where you have one file and you can copy it as many times as you like to propagate it. Money, however, has some particular features which make this most complicated. If I spend $5 I can’t copy it and send it to someone, once I send it, it has to leave my possession. This means that there needs to be a peer-to-peer network with a shared memory. This means you need a byzantine fault tolerant system that can have some sort of consensys to update and maintain this database. 

This happened in 2008 through the mix of game theory, technology and economics. By using a proof of work system, the network can maintain and secure this same truth. The state (database of transactions) is maintained in a linked list most commonly referred to as a blockchain. However, this takes a lot of energy to maintain so there is an incentive for users to maintain this which was the underlying cryptocurrency bitcoin. 

In 2014 Vitalik Buterin created a new similar network which allowed code to be sent to this shared database. This allowed for smart contracts to run on this platform. Smart contracts are code that can be executed if certain specifications are met automatically. For example in the case of a marketplace, if products are delivered the deliverer receives the funds. This is BRM’s current implementation.

The final piece of this puzzle is Interplanetary File System or IPFS. Since maintaining a shared database takes a lot of energy, it is prudent to keep the least amount of information possible on the blockchain. IPFS is a new protocol to replace HTTP. Instead of going to a server files will be shared in a peer to peer network similar to that of Bitcoin’s. Since one version of the database is not needed there is no energy needed to find one state and files can be stored. To find a file on IPFS you need the Hash that is created when a file is initially stored. 

Together with Ethereum and IPFS a truly decentralized database can be created in the vision of the cypherpunks of the 90s. However, some types of data are sensitive and fail in an anonymized marketplace. Thus online identities are important. Thus we are creating a marketplace that is peer to peer with identity verification. 

Problem statement 

According the National Institute of Health of the United Kingdom, the average grant for researchers is about $500,000. Researchers often spend much of this money and their time collecting data that has already been gathered. Once data has been collected, there is often no incentive for them to share it with other researchers.
Furthermore there is little incentive for a researcher to recollect someone else's data “Reproducibility is not well understood because the incentives for individual scientists prioritize novelty over replication”
(http://science.sciencemag.org/content/349/6251/aac4716)

Solution

What we propose is to incentivize the researchers to store their data on a decentralized network. This will facilitate the creation of a marketplace for basic research data that can be extensive and searchable. 

We believe that this can create scenarios that push forward the state of scientific research on this planet as data can be shared easily, cheaply and viewed and analyzed from different view points. This will also create incentives for labs to just create new data for no purpose but to sell and as long as the lab was approved by the publishers of journal articles we can feel confident in the data being published. Staying true to David Ricado's comparative advantage. Finally, if we cap how many times one set of data can be used we will have created an incentive for researchers to recollect said data therefore building in an incentive for repeatability something that is lacking in the scientific world.


Addressing possible concerns 

One issue of which we are cognizant is that if we are to incentivize the sharing of good research data, we will also be incentivising the sharing of false research data. It is not enough for us to trust that the transactions will happen but we have to trust who we are dealing with. To solve this, we will build an identity layer on the back-end that connects to a front-end social-media-like solution where the researcher’s name, previous publications and whatever else may be needed can be known to everyone. Most importantly, part of the data set must have been used in a peer-reviewed article and the article must be linked. The idea is that if the data was trusted once, it can be trusted again. 

Marketing plan 

To start the monetization cycle, BRM aims to obtain administrative health data from the Canadian government in a bid to attract a base of users. Once these users have been introduced to the platform, the focus would be to communicate with these parties in order to collect information about their other needs. Utilizing this information, BRM will match researchers to users to drive commerce on its platform.

<img src="https://i.imgur.com/swsRERJ.png"
     alt="Markdown Monster icon"
     style="float: left; margin-right: 10px;" />
https://i.imgur.com/swsRERJ.png


Monetization

Once the initial injection of data is complete, the BRM will provide an online space that links researchers to end users of information. Users will transfer funds to researchers via Ether with a flat-rate charge applied.

<img src="https://i.imgur.com/4QdPahW.png"
     alt="Markdown Monster icon"
     style="float: left; margin-right: 10px;" />

Another monetization route would be to charge a rate to use our identification layer protocol. The rate would be small not to discourage usage. 

Furthermore, future paths would be going to isolated data silos and putting their research data up and sell them ourselves. For example, health data is scattered along multiple different e-health platforms worldwide. The servers tend to be held by each individual institution. Buying, organizing and anonymizing this data is a multibillion dollar industry. For example, IMS health which has a market cap of around 10 billion dollars does this. This is only one of many companies in this industry.

Finally, we have really created a protocol on top of the ethereum/IPFS networks that allow for the creation of a decentralized identity marketplace. We can thus create an API to make the creation of your own marketplace. We would not charge for the use of the API but input small fees into all of the smart contracts created with it. 

Backend description

The smart contracts will be done on the Ethereum network. 
Tracing the idea from start to finish, a researcher will first create an account, thus creating an Ethereum private-public key pair. The account this will prompt them to go through our identity management system and get verified on the blockchain. They can also use other tools that may be available today like Uport. 
They will then upload their files to the interface. The files would be first encrypted with the user's private keys then stored in IPFS. The hash of the IPFS file will be stored in a smart contract.
The smart contracts will be generated on the fly through the front-end of the dapp. There will be a maximum number of transactions when the contracts are generated before a kill code is triggered, thus to stop the overuse of the data. After the kill code is enacted the front end of the app can keep a running tally of the data used, and there can even be a last price and makeshift bounty page for researchers to retest the data. After a contract is killed, the same IPFS hash cannot be sold again, therefore blocking reuse.
Since the smart contracts are being generated on the fly all new contracts can be updated. In fact, old contracts can be killed by the msg.sender and updated (as long as the front end of the app can realize how many times the data has been bought and therefore can kill the contract at the appropriate time).
Encrypting the data ensures the user ownership but makes it harder to make sure data is not being reused. As well, a person can buy the data and then just share it with others so a piece of research can be reused anyways. It will take community measures outside the app to make sure that research is not being reused. This is not a perfect solution but unlike today adds certain incentives that we do not have.
When an individual goes to buy data they will also create an account and can either pay a fixed price or a bidding price of sorts depending on how the owner of the data set the contract up (they idea is to give the owner as much autonomy as possible). The user will get the hash then the front-end will send a generated transaction from the seller able to decrypt the files. The files will then be available for download.

Our code Implementation

https://ropsten.etherscan.io/address/0x7bd9ecd5dbfa138ccc1e47e1bc9cba4f8fcd41a5