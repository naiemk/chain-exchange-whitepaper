# Chain-Exchange White Paper
**Ferrum**, An exchange protocol across different block-chain technologies

## Abstract
Bitcoin and Ether are examples of major digital currencies on the market today. Currently such digital currencies are traded in traditional centralized exchanges. Etherium provides infrastructure for creating tokens on the Etherium blockchain, hence, such tokens can be exchanged using smart contracts and the transaction will be confirmed within the Etherium blockchain. However, a decentralized exchange of assets across different technologies, such as Bitcoin to Ether exchange is not possible today without modifying the existing blockchain protocols. Additionally, each blockchain technology has its own strengths and weaknesses. The ability of freely moving within technologies can prove extremely useful. In this paper we propose a new intermediate network and exchange system which can be pegged to other digital assets or used as exchange medium between different assets with different decentralized transaction management technologies. We discuss a protocol called **Ferrum** and its implemented cryptocurrency called ***Fe***. The value of every *Fe* is pegged to one or a portfolio of various other crypto-currencies and it can be converted to or from the underlying cryptocurrencies it represents.  We propose an implementation of *Ferrum* on a Tangle (based on IOTA tangle), hence, people can convert their Bitcoins to Fe equivalent and execute countless free transactions on the *Ferrum* network. They can further convert their *Fe* back to any other originating crypto-currency supported by the *Ferrum* network.
 We utilize concepts that we call **Proof of Burn**, **External Wallet**, and **Futures** to enable the exchanges without relying on a centralized market maker.

## Introduction

Crypto-currencies such as Bitcoin and Etherium have recently got so much press that there is no need for an introduction to the concepts of block-chain and crypto currencies. Readers can refer to [wiki-blockchain] for more information. The price of bitcoin has seen phenomenal growth recently and attention of public and institutional investors have significantly increased the potential of using top crypto-currencies as store of value for long term. Additionally, the world of block chain and crypto-currency is widely elemental with hundreds of different coins and distributed ledgers on the market. The dynamism of innovation in the field is not necessarily compatible with the real capacities of adopting markets, hence; causing survival of a only few winner ideas on the market and death of the majority of innovations. Old-fashion exchanges, which are trust based businesses exist that facilitate exchange of crypto-currencies with serious limitations, but currently there is no organic solution for communities to support their crypto-currencies and they need to rely on various exchanges to adopt their technologies. 

In this paper we propose a distributed exchange protocol called ***Ferrum*** that aims to solve above challenges. *Ferrum* acts as an intermediate network with plugins for exchange with external networks. Every community can write and start using a plugin on the network which would allow them to exchange their currency with willing parties on the network that adopt their plugin, hence; eliminating the need for any trusted party and enabling a truly global and organic exchange.

In the next few paragraphs we present the several challenges in the world of crypto-currencies that motivated the design of *Ferrum*:

- **Bitcoin is not a good curency but is a good store of value**. Bitcoin and a few other major crypto-currencies have established themselves as store of value. This is great news for the world of crypto-currencies. We can think of Bitcoin as **gold** in the real-world. The scarcity of gold has made it a global store of value that can be used to back the value of other assets, however gold cannot be practically used in day-to-day transaction. Although it is possible to conceive a world in which people buy their morning coffee by passing a miniscule particle of gold to the barista, it is not a probable outcome. We need a crypto-currency (*Fe*) that can be backed by (pegged to) Bitcoin that can scale and can be transacted with ***zero*** fee, and hopefully without producing too much greenhouse gases in the process. *Fe* should be freely and reliably converted to and from Bitcoin, or other crypto-currencies without volatility. It is important for the pegged transaction to present no volatility in value in relation to the external crypto-currency it represents, however there could be a fee for transacting between *Fe* and the external crypto-currency. The promise of the **Ferrum** network is that with enough liquidity people would not need to transfer their currencies back to the external crypto-currency often. *Fe* can be used as a token for spending Bitcoin (BTC) or other crypto-currencies. For example if a coffee costs *BTC* 0.0002, consumer will pay the amount of coffee in *BTC* to the seller, but the transaction happens in milliseconds over the *Ferrum* network, hence, no transaction fee.

- **Exchanges are not decentralized** The promise of block chain and crypto-currencies were to provide a decentralized network for peer to peer transactions, but in reality majority of crypto-currencies are held and transacted at a few big companies and exchanges such as Coinbase. The current situation is far from the premised world of decentralized transactions and community owned currencies and is more like a traditional, but less effective banking system (hence scalability issues and expensive transaction fees). There is clearly a need for a decentralized exchange where once can contribute to the system without no need to trust or rely on giant corporations. This is by far the biggest failure of crypto currencies and the need to address this problem is felt by the community and consumers. Ideally between the multi-billion dollar crypto currency world, transfer of value should be able to happen without the need to resort back to fiat currencies or traditional trust-based organizations. *Ferrum* network can fill this gap by providing an intermediate network for exchange of values across different crypto-currencies.

- **Regulatory risks in technology proposals** Many proposals and white papers over existing or new decentralized transaction systems rely on nodes acting certain tasks which are parallel to roles of a money transmitting agent, a market maker, or other roles. It is important to know that by giving roles such as market maker to the nodes, they could become subject of regulatory risks. In many places in the world, the regulatory framework regarding to the crypto-currencies is in development and it is very likely that governments could start recognizing and regulating crypto-currency transactions. Therefore a market maker in a blockchain network might be subject to licenses, fees, or liabilities. We believe it is important that any exchange proposal does not introduce roles for nodes or wallets other than validating peer-to-peer transactions.

- **Tax consequences** Once governments classify crypto-currencies as assets or currencies, it is possible that they might want to regulate or tax transactions between different crypto-currencies and tokens. Our proposal (*Fe*) is not technically a crypto-currency of its own. Instead it is a surrogate of external currencies which can be transacted on an intermediate network. Please note that this is not a legal advice and merely a description of what *Fe* is in relation to the external crypto-currencies it represents.

*Ferrum* network and *Fe* are designed to solve above problems. In the rest of this paper we propose the *Ferrum* network and its essential concepts. 

## The ***Ferrum*** network

In a general form, *Ferrum* network is a peer-to-peer distributed network with a consensus protocol in which the following statements are true:

- **Read-only access to other external networks**. All or some agents on a *Ferrum* network should be able to read information from one or more external networks. For example a *Ferrum* agent could validate transactions from the Bitcoin blockchain.
- **Irreversible transactions into the network from an external network**. There must be a method of transacting into the *Ferrum* network from external networks - such as sending Bitcoins into the *Ferrum* network. Such transactions cannot be reversible, meaning the originator cannot double spend the Bitcoins or undo the transaction. Such guarantees should be made possible without modification of the external network.
- **Delayed transactions**. A transaction on the *Ferrum* network can be delayed. We call such transactions *Futures*. A future transaction can be considered void after the agreed-upon time is reached, if the condition of transaction is not met. For the *Ferrum* network it suffices to limit the underlying condition to the "completion of another transaction". This is a special case of smart contracts, but for *Ferrum* network to work as a distributed exchange, no custom contract other than the above (*Futures*) needs to be implemented.

### The *Fe*

The subjects of transactions on the *Ferrum* network is *Fe* which, for the lack of better world we refer as *Token* or *Crypto-currency*. *Fe*, however, is not a crypto-currency on itself. Instead the value of *Fe* is a function of the values of external crypto-currencies it represents. To clarify, imagine the following scenario:

Alice generates 1 *Fe*s by transferring one Bitcoin to the *Ferrum* network. She then generates another *Fe* by transferring one Ether to the *Ferrum* network. Alice now has 2 *Fe*s but her total wealth is 1 Bitcoin and 1 Ether. We represent Alice's wealth as "1 Fe(Bitcoin)+ 1 Fe (Ether)". The general form of Alice's wealth is *Sigma_i(a_i.Fe(i))* where *i* is the external cryptocurrency and *w_i* is the amount for *i*. In-fact a *Fe* wallet is nothing but a surrogate for a portfolio of external cryptocurrencies.

Alice then sends all of her Fe(Ether), plus 50 percent of her Fe(Bitcoin) to Eve for her birthday gift. Alice now has only 0.5 Fe(Bitcoin), and Eve has 1 Fe(Ether) and 0.5 Fe(Bitcoin). Eve can decide to get back some actual Bitcoins by engaging in a *Future* transaction with Mike. The future transaction can be described as: "Transfer 0.5 Fe(Ether) from Eves Fe wallet to Mike's Fe wallet, under the following condition; Transfer of 0.5 Bitcoin from Bitcoin Wallet W0 to Bitcoin Wallet W1 has happened before tomorrow 12:00pm". Wallets W0 and W1 are Bitcoin wallets where Mike and Eve have agreed upon before starting the *Future* transaction. If the external transaction is completed before the agreed time, Eve's *Fe*'s would be invalidated and Mike would own 0.5 Fe(Bitcoin). Otherwise *Fe*'s would be release back to Eve and Mike ends up with nothing.

The Future transaction is limited by the *Ferrum* network, such that Bitcoins can only be transacted with *Fe(Bitcoin)* of the exact same value. Although *Fe(Bitcoin)* can freely be transacted by *Fe(Ether)*, external futures are constrained by the network.
The obvious question here is what motivates Mike to converts his Bitcoins to *Fe(Bitcoin)*? Once the *Ferrum* network achieves enough maturity the only motivation that Mike needs is access to *Fe* which would allow him to buy goods or exchange crypto-currencies without fees, but until such level of maturity is achieved an inceitive system needs to be implemented. We propose several inventive ideas in the later sections of this paper.  

### External Network Plugins

### External Wallets

### Proof of Burn

### Futures

### (Tracing the) Value of *Fe*

### Incentives


## Implementation

### IOTA Tangle

### APIs


### *Fe* Value Validation Algorithm


## Conclusion




