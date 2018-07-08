This is an exhaustive list of cryptoeconomic mechanisms currently used for stability in tokenized units of account. 

```

**Stability Mechanism Name**

(type of mechanism)

General comments

Pros:

Cons:

Source:
```

**Tokenized IOU Coupons**

(single-token, no expansionary/retractionary cycle)

The original stability mechanism by simply holding 1:1 of the pegged asset and simply tokenizing it. Tether is a successful example. 

Pros: No other mechanism or second token is needed to keep stability to a pegged asset. 

Cons: Requires trust to create IOU tokens of off-chain assets.

**Seigniorage Share/Seigniorage Equity**

(two-token, expansionary/retractionary cycle)

The first proposal for an asset-less stability mechanism. A seigniorage share represents equity in the future growth (future seigniorage) of the network that issues the stable tokens. During expansionary cycles, the share token holders can exchange their shares for stable tokens in an open auction. 

Pros: Does not require assets for stability mechanism. 

Cons: A seigniorage share only represents future growth (ie: future issuance) of more stable tokens and nothing else. It does not represent any other network asset or metric. Share holders get diluted as more is printed during expansionary cycles. 

**Basis Bond**

(two-token, expansionary/retractionary cycle) *note: basis has a 3rd token in the system but does not serve any role as a stability mechanism, so Basis Bonds are labeled as "two-token" mechanism.*

A token proposed in the basis.io system which is auctioned off to retract supply of the stable token. The "bond token" pays back exactly 1 stable token during an expansionary cycle. Bond token holders are paid out in a first in first out queue during expansionary cycles. Basis bonds expire in 5 years if not paid back. 

Pros: A very simple mechanism modeled after seigniorage shares with an expiry date. 

Cons: Doesn't behave similar to a classical "bond" in traditional banking. Secondly, because of the first in first out queue, bond tokens are not fungible so creating a market on exchanges for bond tokens becomes unnecessariy difficult. 

**Decentral Bank Coupon Bond**

(two-token, expansionary/retractionary cycle)

A token proposed in the decentral bank system which is auctioned off to retract supply of the stable currency token. It pays the holder stable tokens at the coupon rate of the bond at even intervals until maturity date/block height.

Pros: Behaves as a classical bond in traditional banking. Pays out at even intervals independent of future stable token expansions. All bonds with same coupon rate and same maturity date are fungible. 

Cons: Decentral bonds pay out even if stable tokens don't need to expand, meaning new bonds have to be printed again to subsidize older bond holders if the supply of the stable currency needs to remain low. 

**Decentral Market Making**

(Market making)

A market making method proposed by the decentral bank system where participants deposit funds (such as ETH) into the bank and are paid interest in the stable currency token. The bank then uses the deposited funds to place market making orders for the stable token at the stability price range. Interest rates can be adjusted to incentivize more deposits for more market making orders. 

Pros: No on-chain identity layer required for using this bank service and earning interest (unlike other loan based options). The more funds in the bank, the larger endowment for market making and more difficult to break the currency stability. Interest rates can be increased to incentivize more deposits. 

Cons: This method is essentially a classical fractional reserve - although it is publicly auditable. A bank run is possible if majority of depositors want their funds back. Some kind of insurance for depositors would be preferable such as insuring all deposits in the stable currency in case of a bank run.  

**Carbon Credit**

(two-token, expansionary/retractionary cycle)

A token proposed in the carbon.money system which is auctioned off to retract supply of the stable token. Carbon credits are never removed from circulation (unlike Basis bonds and seigniorage shares). During expansionary cycles, the stable token is simply paid to carbon credit holders pro rata as a de facto dividend. 

Pros: Even more simple than seigniorage shares and basis bonds. 

Cons: Psychological feeling of never-ending dilution of credit tokens since they are never taken out of circulation. 

**Overcollaterized debt**

**Transaction fee burn/sinks**

**Stability fee sinks**
