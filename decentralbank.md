# Decentral Bank: A Peer-to-Peer Central Bank and Stable Currency System
S.R.A. Lee (ETH: 0x104c664DFAE84f43932198e3c553F783F7bA8b80)

##Abstract

We propose a purely permissionless, borderless "world bank" which functions analogously to a central bank and conducts all its operations purely on distributed ledger networks. Decentral Bank equity holders vote on what actions to perform during open market operations. The bank can accept deposits in cryptographic assets, pay interest to depositors, and print its own cryptographic fiat currency. Depository branches of this world bank are smart contracts on general compute ledger platforms such as Ethereum.

To expand the money supply, any bank branch can print money and auction it off for assets. To contract the money supply, the bank can sell assets, print bonds, or print equity tokens to sell for money. Equity token holders decide the interest rate and when to expand or contract the bank's money supply. The rational, economic goal of this banking network is to accrue the most profitable assets and stabilize its printed currency to reach worldwide ubiquity. 

##Overview

A decentral bank is a completely "on-chain" (residing on a distributed ledger platform) network of bank branches that accept deposits in assets and pays interest to depositors in printed currency. Each branch of a bank is a smart contract that resides on a particular distributed ledger/blockchain platform and accepts a variety of deposits and prints currency. The smart contract listens for the current state of other bank branches' smart contracts to trustlessly communicate between branches using atomic swaps and other cross-ledger protocols. 

The bank uses deposited assets and equity to expand and contract the money supply to achieve stability of the decentral bank notes it prints. Bank equity holders vote on the interest rates paid for deposits of different assets, changing the rates depending on risk and the liabilties of the bank. The bank can sell these assets to contract the currency supply at any time if necessary. Since depositors have the right to withdraw their asset at any time (like a normal bank), it is prudent to keep verifiable reserve requirements that are programmed into the smart contract of each branch's code. This way, depositors can transparently audit the branch at any time. The bank can also print bond tokens which pay out a consistent coupon plus interest agreed by equity holders. This provides another mechanism to retract the supply of currency by offering riskless future returns denominated in the decentral bank currency. 

##Technical Specifications

Equity holders interact with the equity smart contract by calling the monetary_policy() function to vote for new policy at each voting period X. The function takes 3 arguments. The address variable designates the bank branch the policy is referring to. The currency_policy variable is a positive or negative integer which designates whether the branch should expand (if positive) or retract (if negative) the currency token and by how much. The interest_rate is the interest paid to depositors of that branch's assets. 

monetary_policy(address, currency_policy, interest_rate)

Equity holders can also change the bond_rate variable during each voting period X which denotes the interest rate paid to bond holders across all branchs in the network. 

bond_policy(bond_rate)


In order for the bank's money to be truly fungible, bank branches across all ledgers need to be able to communicate with one another in a purely trustless fashion using atomic swaps and state channel communications. 

A sample Ethereum branch is shown below with comments. This contract accepts ETH and prints currency. Each branch can handle a single on-chain cryptographic asset and is opened by equity holders. 

Example Ethereum branch:

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

##Discussion 

A decentralized bank which holds only cryptographic assets was not possible before the proliferation of general compute ledgers which created an environment for many different types of on-chain assets. Additionally, advancements in trustless interblockchain/inter-ledger communication was required before a decentralized banking entity could hold many assets across different ledgers, all controlled by the bank's shareholder tokens. 

Uncompromosing censorship resistance is the defining characteristic of this network. The cryptographic technology used to produce this peer-to-peer financial system would need to be continuously updated to remain on the bleeding-edge so as to supercede nation-state level regulation and control in order for the system to produce a world-scale banking market. Otherwise, its chief utility proposition is dubious compared to centralized, nationalized central banking systems. 

Decentral bank offers any individual in the world reliable interest on deposited assets, access to a stable cryptographic currency with sound monetary policy, by-definition riskless bond coupons, and equity investment opportunities in the bank itself. 
