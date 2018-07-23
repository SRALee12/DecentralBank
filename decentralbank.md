# Decentral Bank: A Peer-to-Peer Central Bank and Stable Currency System
S.R.A. Lee (ETH: 0x104c664DFAE84f43932198e3c553F783F7bA8b80)

sralee@protonmail.com

## Abstract

We propose a purely permissionless, borderless "world bank" which functions analogously to a central bank and conducts all its operations purely on a distributed ledger network. The bank can accept deposits in cryptographic assets, pay interest to depositors, print and sell bonds, print equity, and print its own cryptographic fiat currency. These services allow for the bank to manipulate the printed money supply to keep it within a stable price range. 

Decentral bank's many stability mechanisms help perform the most diverse range of monetary policy possible on its printed currency tokens which act as a stable unit of account, store of value, and medium of exchange. 


## Definitions 

**Decentral bank:** A peer-to-peer network which prints a stable currency and conducts a variety of trustless, on-chain open market operations. 

**Decentral open market operations (DOMO):** The activities that decentral bank undertakes to expand or retract the network's currency supply. Activities include changing the interest rate on different deposits, changing the bond interest rate, expanding or contracting the currency supply through asset repurchase of currency. Equity holders can implement new stability mechanisms and market operations through hard-fork updates.  

**Currency:** A token which serves as a unit of account and medium of exchange printed by decentral bank. The network expands and contracts the currency supply to keep the currency at a stable purchasing power, similar to classical banknotes, so that they can be used as practical money. All currency is fungible between different bank branches.   

**Bond:** A debt instrument printed by decentral bank which can be purchased with currency. Branches print bonds to retract the currency supply. The bond pays out a denominated amount at a fixed interval (the coupon). Bonds printed at any bank branch print out at the same global rate which can be adjusted programmatically. 

**Asset-Currency Repo (AC Repo):** A market making service conducted with decentral bank deposited assets to keep the currency price at the desired range of stability. Assets are sold off at the stability price. Sell orders of assets for currency act as market-making operations to remove currency from circulation.    

**Decentral equity:** A token in the decentral bank network which gives right of proportional ownership to holders. The equity tokens are a staking token and the main unit of the decentral bank blockchain. 51% of equity holders create canonical chain consensus. Equity holders have governance say on aspects of open market operations in the network through the fork choice consensus process. This means that the interest rate paid out to depositors of different assets, the global bond rate, when to expand or contract the currency supply, which assets to buy when printing new currency, and what algorithms are used to decide the above can be decided by new hard forks of the network through equity holder consensus. 

**Stability mechanism:** A particular scheme used to exert monetary policy so that currency tokens remain stable. Usually a stability mechanism is a scheme for either contracting the currency supply, backing the currency tokens with collateral, or market making the currency at a defined price range. 

**Fork choice rule:** A set of instructions for choosing the canonical, longest chain of blocks of a particular blockchain database. In the decentral bank network, the canonical chain is the chain of blocks which the Byzantine method has defined. 

## Overview

A decentral bank is a completely "on-chain" (residing on a distributed ledger platform) network which employs a large number of stability mechanisms to exert maximum leverage on manipulating the currency supply which it prints. 

Decentral bank uses a number of policies which allow for expansion and retraction of the currency tokens so that the price of the currency remains at a constant bound. Unlike other stable token schemes, decentral bank employs multiple market operations, similar to a real central bank. However, unlike a classical central bank, the market operations are algorithmically fair and transparent since they take place completely on the blockchain itself with no off-chain component needed.  

The bank has 3 main stability mechanisms used to retract currency supply. Firstly, the bank continuously sells decentral bank bond tokens purchasable with currency tokens. This destroys the currency tokens and pays back the holder of the bond token a coupon rate until maturity of the bond. This bond auction is always algorithmically available to purchasers and the network software adjusts the maturity date 

Secondly, the network auctions off currency for certain assets on different networks using cross-chain communication and holds those assets in smart contracts on their respective networks. For example, decentral bank could accept ETH on the Ethereum main network. 

The type of assets that decentral bank can accept can be changed with a hard fork update to the client software which means 51% of the staking tokens (equity tokens) must accept such an update. 

Lastly, decentral bank can auction of newly created equity tokens for currency to take currency out of circulation. This is the final stability mechanism employed by decentral bank. Equity token auctions would be algorithmically activiated if a large amount of currency must be retracted from the circulating supply in a certain time period. 

The bank uses deposited assets and equity to expand and contract the money supply to achieve stability of the decentral bank notes it prints. The bank sells deposited assets in a currency repurchase market-making operation to contract the currency supply at any time at the pegged price of the currency. Since depositors have the right to withdraw their asset at any time (like a normal bank), it is prudent to keep verifiable reserve requirements that are programmed into the client software. This way, depositors can transparently audit the network at any time so that the fractional reserve nature of decentral bank is public and auditable. The bank can also print bond tokens which pay out a consistent coupon plus interest. This provides another mechanism to retract the supply of currency by offering riskless future returns denominated in the decentral bank currency. 

## Technical Specifications

The Decentral Bank main network uses Ethereum open source software for a lot of the foundational consensus designs and mechanisms. A fork of the Ethereum core client is the starting point of the Decentral Bank core client with turing complete smart contract functionality disabled. The Decentral Bank core client would run a series of banking contracts on the main network. Essentially, it is a singleton machine implementation of the Ethereum main network where the contracts running are stability mechanisms for the printed currency (and other banking functions). 

## Fork Choice Rule as Governance

Decentral Bank equity holders control the implicit end-state of the network through their ability to hardfork the canonical chain should sufficient social consensus arise among equity token holders. Since certain stability mechanisms used by the decentral bank network hold cryptographic assets, the canonical chain retains control of such stored assets and thus keeps the network effect. 

## Scalable, Plasma Cash Currency 

Decentral Bank should become the world's de facto currency-issuing bank. In such a world, the number of transactions required for the currency would be orders of magnitude larger than current distributed ledger can handle. For this reason, the Plasma Cash framework proposed by the Ethereum foundation would be an ideal scaling solution for purely fungible currency tokens. Secondly, "plasma chains" can be run by institutions with sufficient merkle proofs to the Decentral Bank main network. 

## Truly Private Currency 

Since decentral bank currency is a fungible token, it would be possible to integrate distributed ledger privacy features such as zero knowledge proofs which would allow for any user to exchange stable currency tokens without revealing their identity. Such zero knowledge proofs without a "set up" phase are still in development and are not widely available, but can be incoporated into the client software once software has advanced. 

## Transaction Fees

Movement of currency tokens, bond tokens, and equity on the decentral bank network requires transaction fees. In a proof of stake based consensus mechanism, the equity tokens are the staking token and take part in the block proposal and finality process. Thus, equity holders that stake their tokens recieve the revenue accrued from transaction fees from users. 

## Comparisons, Criticisms, and Alternatives

Decentral bank is a network of banks which print currency and accrue assets to expand and retract the currency supply, thus achieving price stability. Other projects have proposed such price stability through expansion and retraction of a currency token. However, we believe that most leading projects are lacking in the ability to accrue assets to conduct meaningful open market operations similar to a traditional banking entity which issues its own currency. Without proper open market operations, the entire system is built on a faulty premise and foundation. 

There are an emerging class of algorithmic stable currency projects. Each of these systems usually hinge on a 2 token scheme. One token being the object of stabilization while the other token being the object of risk where the holder assumes liability for negative value in order to gain positive value of the system. This 2 token system first proposed by Robert Sams in 2014 is the essence of most algorithmic based stable currency projects. 

### Seigniorage Shares

Seigniorage shares is the seminal paper by Robert Sams in 2014 that describes the famous two token system of shares and coins. Coins being the object of stabilization and shares being the object of risk (with downside and upside potential). Sams explains: "When coin supply needs to increase, coinbase is distributed to share holders in exchange for a certain percentage of shares, which are destroyed (coin supply increases, share supply decreases). When coin supply needs to decrease, sharebase is distributed to coin holders in exchange for a certain percentage of coin, which are destroyed (coin supply decreases, share supply increases)."

Sams contends, "I suggest that there needs to be two types of coin: coin that acts like money and coin that acts like shares in the system’s  seigniorage." Seigniorage is defined as profit made by a government when they issue/sell/loan the currency which they print and bring into existence. What is interesting about Sams' scheme is that it cannot hold seigniorage. There is no actual way for this system to hold assets or any type of seigniorage that is attained by auctioning off newly printed coins. The main issue we take with this approach is that there cannot be a token which "acts like shares in the system's seigniorage" if the system is incapable of holding actual seigniorage. This token simply defaults to a future potential of return for an expansion in the system. What is interesting is that Sams clearly understands that the main attraction of the shares token is the "profit from future coin expansions" but does not address that a system with real seigniorage means that share tokens have substantially more utility and value. This is because the value of shares would no longer just be the profit of future currency expansions but profit from the increase in value of all assets owned by the system. This includes pricing in future expansions of currency as well as the assets held within the nework which was bought by currency at previous expansions. A system which can actually hold seigniorage is a system which can issue shares/equity of such seigniorage, not a system which is designed with the sole inability to hold seigniorage. 

The object of risk in the seigniorage shares system can only gain a positive value if the system expands. Conversely, decentral bank equity (the object of risk in our system) can gain a positive value if the net value of assets held in the system increases **and/or** the system needs to expand the currency supply. Thus, there is substantially more upside potential to the object of risk in the decentral bank system than seigniorage shares. 

### Basecoin/basis.io 

Basis is a project which has as of May 2018 raised $133m USD. The scheme has 3 tokens instead of 2. Basecoin/basiscoin is the object of stabilization. Basis bonds are the tokens of risk which are printed and auctioned off when coins need to retract in supply. Finally, baseshare tokens are merely investor tokens and serve no use in open market operations of the basis system. They are merely a tool to raise funds for the project (as evidenced by their large and successful funding round). So in reality, the economic scheme is almost identical to seigniorage shares and is actually a 2 token system.  

Bond tokens in the basis system are a misnomer. Bond tokens do not pay out a coupon or mature on a given date but instead pay out in a peculiar and unconventional first-in-first-out queue when the system expands the currency supply. Bond tokens are essentially seigniorage share tokens with a different name and payment distribution scheme. Even worse, unlike seigniorage shares, bond tokens are not fungible since they have a unique place in the first-in-first-out queue to be repaid. This further means that unlike seigniorage shares (or real government bonds), basis bond tokens are not listable on exchanges and trading pairs cannot form since each one is unique. There is an inability to form efficient basis bond markets which creates even further liquidity risk. 

Not only is this not how a traditional bond functions, it is intentionally (or maybe unintentionally) confusing users of the system into believing it has some kind of substantial similarity to central bank bonds. In fact, the **only** similarity basis bonds have with traditional bonds is that they are used for retraction of currency. All other similarities stop there. Calling basis bonds "bonds" is a misnomer at best or a marketing ploy at worst. Traditional bonds are riskless by definition. That is, the government will always pay the holder the face value of the bond since they can simply print currency to do it (even if the currency loses purchasing power because of such printing). Basis bonds have no such guarantee. In fact, they are the object of risk - a complete opposite utility to that of government bonds which are traidtionally thought of as "riskless by definition." 

Basis dubs itself as a "stable cryptocurrency with an algorithmic central bank." Basis is more akin to a currency with an empty central bank with no way to accrue a balance sheet of assets. The Basis scheme imitates a central bank with zero options when conducting open market operations but to sell bonds (which as we discussed above is not really a bond). Essentially, the basis system might seem similar to central banking on a cursory level, but it could not be farther from. 

## Discussion 

A decentralized bank which holds only cryptographic assets was not possible before the proliferation of general compute ledgers which created an environment for many different types of on-chain assets. Additionally, advancements in trustless interblockchain/inter-ledger communication was required before a decentralized banking network could hold many assets across different ledgers, all controlled by the bank's equity tokenholders. Additionally, with the practical implementation of atomic swaps and cross-chain trustless state verification, it is possible for the stable bank currency to be fungible across many different legders which it is printed on.  

Uncompromosing censorship resistance is the defining characteristic of this network. The cryptographic technology used to produce this peer-to-peer financial network would need to be continuously updated to remain on the bleeding-edge so as to supercede nation-state level regulation and control in order for the system to produce a world-scale banking market. Otherwise, its chief utility proposition is dubious compared to centralized, nationalized central banking systems. 

## Conclusion

Decentral bank offers any individual in the world reliable interest on deposited assets, access to a stable cryptographic currency with sound monetary policy, by-definition riskless bond coupons, and equity investment opportunities in the bank itself. 
