This is an exhaustive list of cryptoeconomic mechanisms currently used for stability in tokenized units of account. 

**Tokenized IOU Coupons**
The original stability mechanism by simply holding 1:1 of the pegged asset and simply tokenizing it. Tether is a successful example. 

Pros: No other mechanism is needed to keep stability to a pegged asset. 

Cons: Requires trust to create IOU tokens of off-chain assets.

**Seigniorage Share/Seigniorage Equity**

The first true proposal for an asset-less stability mechanism. A seigniorage share represents equity in the future growth (future seigniorage) of the network that issues the stable tokens. During expansionary cycles, the share token holders can exchange their shares for stable tokens in an open auction. 

Pros: Does not require assets for stability mechanism. 

Cons: A seigniorage share only represents future growth (ie: future issuance) of more stable tokens and nothing else. It does not represent any other network asset or metric. Share holders get diluted as more is printed during expansionary cycles. 

**Basis Bond**

A token proposed in the basis.io system which is auctioned off to retract supply of the stable token. The "bond token" pays back exactly 1 stable token during an expansionary cycle. Bond token holders are paid out in a first in first out queue during expansionary cycles. 

Pros: A very simple mechanism modeled after seigniorage shares. 

Cons: Doesn't behave similar to a classical "bond" in traditional banking. Secondly, because of the first in first out queue, bond tokens are not fungible so creating a market on exchanges for bond tokens becomes unnecessariy difficult. 

**Decentral Bank Coupon Bond**

A token proposed in the decentral bank system which is auctioned off to retract supply of the stable currency token. It pays the holder stable tokens at the coupon rate of the bond at even intervals until maturity date/block height.

Pros: Behaves as a classical bond in traditional banking. Pays out at even intervals independent of future stable token expansions. All bonds with same coupon rate and same maturity date are fungible. 

Cons: Decentral bonds pay out even if network still needs retracted supply, meaning new bonds have to be printed again to subsidize older bond holders if the supply of the stable currency needs to remain low. 

**Decentral Market Making**

A market making method proposed by the decentral bank system where participants deposit funds (tokens such as ETH) into the bank and are paid interest in the stable currency token. The bank then uses the deposited funds to place market making orders for the stable token at the pegged price range. Interest rates can be adjusted to incentivize more deposits for more market making orders. 

Pros: The more funds in the bank, the larger endowment for market making and more difficult to break the currency peg. Interest rates can be increased to incentivize more deposits. 

Cons: This method is essentially a classical fractional reserve - although it is publicly auditable. Bank runs possible if majority of depositors want their funds back. Some kind of insurance for depositors would be preferable such as insuring all deposits in the stable currency in case of a bank run.  

**Carbon Credit**

**Overcollaterized debt**

**Transaction fee burn/sinks**

**Stability fee sinks**
