### Requesting Data
To add Market Cap dataset by Coin Gecko to your algorithm, use the AddData method to request the data. As with all datasets, you should save a reference to your symbol for easy use later in your algorithm. For detailed documentation on using custom data, see [Importing Custom Data](https://www.quantconnect.com/docs/algorithm-reference/importing-custom-data).

Python:
```
class CoinGeckoMarketCapAlgorithm(QCAlgorithm):

    def Initialize(self):
        self.SetStartDate(2020, 10, 7)
        self.SetEndDate(2020, 10, 11)
        self.SetCash(100000)

        var coingecko_marketcap_symbol = self.AddData(CoinGeckoMarketCap, "BTC").Symbol
```

C#:
```
namespace QuantConnect
{
    public class CoinGeckoMarketCap: QCAlgorithm
    {
        public override void Initialize()
        {
            SetStartDate(2020, 10, 7);
            SetEndDate(2020, 10, 11);
            SetCash(100000);

            var coingecko_marketcap_symbol = AddData<CoinGeckoMarketCap>("BTC").Symbol;
        }
    }
}
```

### Accessing Data
Data can be accessed via Slice events. Slice delivers unique events to your algorithm as they happen. We recommend saving the symbol object when you add the data for easy access to slice later. Data is available in Daily resolution. You can see an example of the slice accessor in the code below.

Python:
```
def OnData(self, slice):
        data = slice.Get(CoinGeckoMarketCap)
        if data:
            marketcap = data[self.coingecko_marketcap_symbol]
            self.Log(marketcap.ToString())
```

C#:
```
public override void OnData(Slice data)
{
    var data = slice.Get<CoinGeckoMarketCap>();
    if (!data.IsNullOrEmpty())
    {
        var marketcap = data[coingecko_marketcap_symbol];
        Log(marketcap.ToString());
    }
}
```


### Historical Data
You can request historical custom data in your algorithm using the custom data Symbol object. To learn more about historical data requests, please visit the [Historical Data](https://www.quantconnect.com/docs/algorithm-reference/historical-data) documentation. If there is no custom data in the period you request, the history result will be empty.

Python:
```
history = self.History(coingecko_marketcap_symbol, 10, Resolution.Daily)
```

C#:
```
var history = History(new[]{coingecko_marketcap_symbol}, 10, Resolution.Daily);
```
