# Decentral Bank: A Peer-to-Peer Central Bank and Stable Currency System
S.R.A. Lee (ETH: 0x104c664DFAE84f43932198e3c553F783F7bA8b80)

sralee@yandex.com

## Abstract

We propose a purely permissionless, borderless "world bank" which functions analogously to a central bank and conducts all its operations purely on distributed ledger networks. Decentral Bank equity holders vote on what actions to perform during open market operations. The bank can accept deposits in cryptographic assets, pay interest to depositors, and print its own cryptographic fiat currency. Depository branches of this world bank are smart contracts on general compute ledger platforms such as Ethereum.

To expand the money supply, any bank branch can print money and auction it off for assets. To contract the money supply, the bank can sell assets, print bonds, or print equity tokens to sell for money. Equity token holders decide the interest rate and when to expand or contract the bank's money supply. The rational, economic goal of this banking network is to accrue the most profitable assets and stabilize its printed currency to reach worldwide ubiquity. 


## Definitions 

**Decentral bank:** A network of bank branches that accept deposits, print a stable currency, and conduct open market operations decided by the network's equity holders. 

**Decentral open market operations (DOMO):** The activities that equity holders agree to take which expands or retracts the decentral bank network's currency supply. Activities include changing the interest rate on different deposits, changing the bond interest rate, expanding or contracting the currency supply by buying or selling assets and deposits. 

**Decentral bank branch (DBB):** A smart contract on a general compute ledger (ie: Ethereum) which accepts deposits in an asset (ie: ETH) and can expand or retract the currency supply. 

**Currency:** A token which serves as a unit of account and medium of exchange printed by decentral bank branches. The network expands and contracts the currency supply to keep the currency at a stable purchasing power, similar to classical banknotes, so that they can be used as practical money. All currency is fungible between different bank branches.   

**Bond:** A debt instrument printed by bank branches which can be purchased with currency. Branches print bonds to retract the currency supply. The bond pays out a denominated amount at a fixed interval (the coupon). Bonds printed at any bank branch print out at the same global rate decided by equity holders.

**Decentral equity:** A token in the decentral bank network which gives right of proportional ownership to holders. Equity holders vote on all aspects of open market operations in the network including the interest rate paid out to depositors of different assets, the global bond rate, when to expand or contract the currency supply, and which assets to buy when printing new currency. Equity holders can delegate out their voting rights to pools or committees that might be better knowledgeable or run programmatic scripts that vote for different operations on their behalf.  

## Overview

A decentral bank is a completely "on-chain" (residing on a distributed ledger platform) network of bank branches that accept deposits in assets and pays interest to depositors in printed currency. Each branch of a bank is a smart contract that resides on a particular distributed ledger/blockchain platform and accepts a variety of deposits and prints currency. The smart contract listens for the current state of other bank branches' smart contracts to trustlessly communicate between branches using atomic swaps and other cross-ledger protocols. 

The bank uses deposited assets and equity to expand and contract the money supply to achieve stability of the decentral bank notes it prints. Bank equity holders vote on the interest rates paid for deposits of different assets, changing the rates depending on risk and the liabilties of the bank. The bank can sell these assets to contract the currency supply at any time if necessary. Since depositors have the right to withdraw their asset at any time (like a normal bank), it is prudent to keep verifiable reserve requirements that are programmed into the smart contract of each branch's code. This way, depositors can transparently audit the branch at any time so that the fractional reserve nature of each branch is public and auditable. The bank can also print bond tokens which pay out a consistent coupon plus interest agreed by equity holders. This provides another mechanism to retract the supply of currency by offering riskless future returns denominated in the decentral bank currency. 

## Technical Specifications

Equity holders interact with the equity smart contract by calling the monetary_policy() function to vote for new policy at each voting period X. The function takes 3 arguments. The address variable designates the bank branch the policy is referring to. The currency_policy variable is a positive or negative integer which designates whether the branch should expand (if positive) or retract (if negative) the currency token and by how much. The interest_rate is the interest paid to depositors of that branch's assets. 

Equity holders can also change the bond_rate variable during each voting period X which denotes the interest rate paid to bond holders across all branchs in the network. 

Example Equity holder contract: 

```
monetary_policy(address, currency_policy, interest_rate)

bond_policy(bond_rate)
```

In order for the bank's money to be truly fungible, bank branches across all ledgers need to be able to communicate with one another in a purely trustless fashion using atomic swaps and state channel communications. 

A sample pseudo-code Ethereum branch is shown below with comments. This contract accepts ETH and prints currency. Each branch can handle a single on-chain cryptographic asset and is opened by equity holders. 

Example Ethereum branch:

```
-----constants-----
 
reserve_ratio = 20 // 20% of total ETH deposited into this branch must always remain in the contract
interest_rate = 2 // 2%, the current interest rate paid yearly to depositors of ETH (calculated paid per block)
bond_interest_rate = 1 // 1%, the current interest rate paid yearly to bond token holders on top of the coupon (calculated per block)

-----public functions-----


deposit_ETH() // deposit any amount of ETH
withdraw_ETH() // withdraw your amount of ETH at any time (provided the bank has enough funds)
collect_interest() // withdraw your earned interest in currency until the current block

-----banking functions-----


set_interest_rate() // equity holders call this function to increase or decrease interest_rate accordingly 
set_bond_rate() // equity holders call this function to increase or decrease bond_interest_rate accordingly
sell_equity_for_ETH() // equity holders call this function to dilute their shares to purchase ETH

expand_currency() // equity holders call this function with argument 1 or 2 and an amount of currency to expand
 1 auction currency for ETH
 2 distribute currency pro rata to equity holders

retract_currency() // equity holders call this function with argument 1, 2, or 3 and an amount of currency to retract
 1 auction ETH for currency
 2 print new equity and auction for currency
 3 auction bond tokens for currency
```

## Comparisons, Criticisms, and Alternatives

Decentral bank is a network of banks which print currency and accrue assets to expand and retract the currency supply, thus achieving price stability. Other projects have proposed such price stability through expansion and retraction of a currency token. However, we believe that most leading projects are lacking in the ability to accrue assets to conduct meaningful open market operations similar to a traditional banking entity which issues its own currency. Without proper open market operations, the entire system is built on a faulty premise and foundation. 

There are an emerging class of algorithmic stable currency projects. Each of these systems usually hinge on a 2 token scheme. One token being the object of stabilization while the other token being the object of risk where the holder assumes liability for negative value in order to gain positive value of the system. This 2 token system first proposed by Robert Sams in 2014 is the essence of most algorithmic based stable currency projects. 

### Seigniorage Shares

Seigniorage shares is the seminal paper by Robert Sams in 2014 that describes the famous two token system of shares and coins. Coins being the object of stabilization and shares being the object of risk (with downside and upside potential). Sams explains: "When coin supply needs to increase, coinbase is distributed to share holders in exchange for a certain percentage of shares, which are destroyed (coin supply increases, share supply decreases). When coin supply needs to decrease, sharebase is distributed to coin holders in exchange for a certain percentage of coin, which are destroyed (coin supply decreases, share supply increases)."

Sams contends, "I suggest that there needs to be two types of coin: coin that acts like money and coin that acts like shares in the system’s  seigniorage." Seigniorage is defined as profit made by a government when they issue/sell/loan the currency which they print and bring into existence. What is interesting about Sams' scheme is that it cannot hold seigniorage. There is no actual way for this system to hold assets or any type of seigniorage that is attained by auctioning off newly printed coins. The main issue we take with this approach is that there cannot be a token which "acts like shares in the system's seigniorage" if the system is incapable of holding actual seigniorage. This token simply defaults to a future potential of return for an expansion in the system. What is interesting is that Sams clearly understands that the main attraction of the shares token is the "profit from future coin expansions" but does not address that a system with real seigniorage means that share tokens have substantially more utility and value. This is because the value of shares would no longer just be the profit of future currency expansions but profit from the increase in value of all assets owned by the system. This includes pricing in future expansions of currency as well as the assets held within the nework which was bought by currency at previous expansions. A system which can actually hold seigniorage is a system which can issue shares/equity of such seigniorage, not a system which is designed with the sole inability to hold seigniorage. 

The object of risk in the seigniorage shares system can only gain a positive value if the system expands. Conversely, decentral bank equity (the object of risk in our system) can gain a positive value if the net value of assets held in the system increases **and/or** the system needs to expand the currency supply. Thus, there is substantially more upside potential to the object of risk in the decentral bank system than seigniorage shares. 

### Basecoin/basis.io 

Basis is a project which has as of May 2018 raised $133m USD. The scheme has 3 tokens instead of 2. Basecoin/basiscoin is the object of stabilization. Basis bonds are the tokens of risk which are printed and auctioned off when coins need to retract in supply. Finally, baseshare tokens are merely investor tokens and serve no use in open market operations of the basis system. They are merely a tool to raise funds for the project (as evidenced by their large and successful funding round). So in reality, the economic scheme is almost identical to seigniorage shares and is actually a 2 token system.  

Bond tokens in the basis system are a misnomer. Bond tokens do not pay out a coupon or mature on a given date but instead pay out in a peculiar and unconventional first-in-first-out queue when the system expands the currency supply. Bond tokens are essentially seigniorage share tokens with a different name and payment distribution scheme.  

Not only is this not how a traditional bond functions, it is intentionally (or maybe unintentionally) confusing users of the system into believing it has some kind of substantial similarity to central bank bonds. In fact, the **only** similarity basis bonds have with traditional bonds is that they are used for retraction of currency. All other similarities stop there. Calling basis bonds "bonds" is a misnomer at best or a marketing ploy at worst. Traditional bonds are riskless by definition. That is, the government will always pay the holder the face value of the bond since they can simply print currency to do it (even if the currency loses purchasing power because of such printing). Basis bonds have no such guarantee. In fact, they are the object of risk - a complete opposite utility to that of government bonds which are traidtionally thought of as "riskless by definition." 

Basis dubs itself as a "stable cryptocurrency with an algorithmic central bank." Basis is more akin to a currency with an empty central bank with no way to accrue a balance sheet of assets. The Basis scheme imitates a central bank with zero options when conducting open market operations but to sell bonds (which as we discussed above is not really a bond). Essentially, the basis system might seem similar to central banking on a cursory level, but it could not be farther from. 

## Discussion 

A decentralized bank which holds only cryptographic assets was not possible before the proliferation of general compute ledgers which created an environment for many different types of on-chain assets. Additionally, advancements in trustless interblockchain/inter-ledger communication was required before a decentralized banking network could hold many assets across different ledgers, all controlled by the bank's equity tokenholders. Additionally, with the practical implementation of atomic swaps and cross-chain trustless state verification, it is possible for the stable bank currency to be fungible across many different legders which it is printed on.  

Uncompromosing censorship resistance is the defining characteristic of this network. The cryptographic technology used to produce this peer-to-peer financial network would need to be continuously updated to remain on the bleeding-edge so as to supercede nation-state level regulation and control in order for the system to produce a world-scale banking market. Otherwise, its chief utility proposition is dubious compared to centralized, nationalized central banking systems. 

## Conclusion

Decentral bank offers any individual in the world reliable interest on deposited assets, access to a stable cryptographic currency with sound monetary policy, by-definition riskless bond coupons, and equity investment opportunities in the bank itself. 
