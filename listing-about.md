### Meta
- **Dataset name**: MarketCap
- **Vendor name**: CoinGecko
- **Vendor Website**: https://www.coingecko.com/


### Introduction

MarketCap by CoinGecko provides marketcap data of the cryptocurrency coins. The dataset covers over 1300 crypto coins that have been listed on CoinGecko website. The data starts in April 2013 and is delivered on a daily frequency.

### About the Provider
CoinGecko provides a data platform, digital currency prices, and fundamental analysis of the cryptocurrency market.CoinGecko was founded in 2014 by TM Lee (CEO) and Bobby Ong (COO) with the mission to democratize the access of crypto data and empower users with actionable insights.

### Getting Started
Python:
```
# Requesting data:
coingecko_marketcap_symbol = self.AddData(CoinGeckoMarketCap, "BTC").Symbol
```

C#:
```
// Requesting data:
coingecko_marketcap_symbol = AddData<CoinGeckoMarketCap>("BTC").Symbol;
```

### Data Summary
- **Start Date**: April 2013
- **Asset Coverage**: Crypto Coins
- **Resolution**: Daily
- **Data Density**: Regular
- **Timezone**: UTC


### Example Applications

The CoinGeckoMarketCap dataset enables researchers to accurately design strategies harnessing marketcap of crypto coins. Examples include:

- As a key statistic, it can indicate the growth potential of a cryptocurrency and whether it is safe to buy, compared to others.
- Investors seeking to add another element to their investment strategies, weighted market cap assessments can be helpful.

### Data Point Attributes

- Marketcap : decimal
