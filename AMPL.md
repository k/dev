# AMPL Liquity Fork

## Required Changes

### Oracle Price Contracts

#### AMPL/USD
Chainlink: 0xe20CA8D7546932360e37E9D72c1a47334af57706

Tellor: 0xe20CA8D7546932360e37E9D72c1a47334af57706
Price Feed Request ID: 10

### ETH -> AMPL operations

All reads of balances need to come from the ERC20 contract.
All sends to be through ERC20 contract
No using msg.value for reading from transactions, needs to be moved to a parameter.

#### Contracts TODO

- [ ] TroveManager 
- [ ] Stability Pool ETH tracking
- [ ] MultiTroveGetter

### Frontend Integration

Need a frontend migration guide for the adjusted borrower operations among other things like reading AMPL balance.

## Optional Changes

### CPI Adjustment

If the minted stablecoin will target AMPL's price target of 2019 dollar, than we will need to incorporate the CPI into the priceFeed to adjust the target collateralization ratios. 

CPI Chainlink Oracle: 0xA1FfB3cB206495eE3fE64E4Ee1A9567da220486E

CPI adjustment code in Ampleforth: https://github.com/ampleforth/uFragments/blob/master/contracts/UFragmentsPolicy.sol#L122
