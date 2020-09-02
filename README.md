你好！
很冒昧用这样的方式来和你沟通，如有打扰请忽略我的提交哈。我是光年实验室（gnlab.com）的HR，在招Golang开发工程师，我们是一个技术型团队，技术氛围非常好。全职和兼职都可以，不过最好是全职，工作地点杭州。
我们公司是做流量增长的，Golang负责开发SAAS平台的应用，我们做的很多应用是全新的，工作非常有挑战也很有意思，是国内很多大厂的顾问。
如果有兴趣的话加我微信：13515810775  ，也可以访问 https://gnlab.com/，联系客服转发给HR。
cdash
=====
A minimalist cryptocurrency portfolio dashboard for the command-line that draws
market data from the [CoinMarketCap][cmc] API.

![screenshot][img]


Installing
----------
1. Visit the [Releases][] page
2. Download the appropriate executable
3. Optionally rename the downloaded executable
4. Optionally place the executable on your system `PATH`


Configuring
-----------
Specify your holdings via a `yml` file structured as follows:

```yml
---
- symbol   : BTC
  holdings : 100

- symbol   : LTC
  holdings : 100

- symbol   : ETH
  holdings : 100
```

By default, `cdash` will attempt to open this file at `~/.config/cdash.yml`. If
you choose to store it elsewhere, provide `cdash` the approriate path using the
`--config` option:

```sh
cdash --config=/path/to/cdash.yml
```

### Ambiguous currency symbols ###
Some cryptocurrency symbols are not unique, which can [cause problems due to
ambiguity][issue-4]. To resolve this, `cdash` also allows currencies to be
specified by CoinMarketCap `id`:

```yml
---
- symbol   : BTC
  holdings : 100

- symbol   : LTC
  holdings : 100

- symbol   : ETH
  holdings : 100

- id       : bitcoin-gold # symbol "BTG"
  holdings : 100

- id       : bitgem       # also symbol "BTG"
  holdings : 100
```

`cdash` will fail with an error if your config file contains references to
ambiguous symbols.


### Specifying the base currency ###
The [base currency][base] may be specified using the `--base` flag. The
following currency codes are supported:

Code  | Currency
------|----------------------
`AUD` | Australia Dollar         
`BRL` | Brazil Real              
`CAD` | Canada Dollar            
`CHF` | Switzerland Franc        
`CLP` | Chile Peso               
`CNY` | China Yuan Renminbi      
`CZK` | Czech Republic Koruna    
`DKK` | Denmark Krone            
`EUR` | Euro Member Countries    
`GBP` | United Kingdom Pound     
`HKD` | Hong Kong Dollar         
`HUF` | Hungary Forint           
`IDR` | Indonesia Rupiah         
`ILS` | Israel Shekel            
`INR` | India Rupee              
`JPY` | Japan Yen                
`KRW` | Korea (South) Won        
`MXN` | Mexico Peso              
`MYR` | Malaysia Ringgit         
`NOK` | Norway Krone             
`NZD` | New Zealand Dollar       
`PHP` | Philippines Peso         
`PKR` | Pakistan Rupee           
`PLN` | Poland Zloty             
`RUB` | Russia Ruble             
`SEK` | Sweden Krona             
`SGD` | Singapore Dollar         
`THB` | Thailand Baht            
`TRY` | Turkey Lira              
`TWD` | Taiwan New Dollar        
`USD` | United States Dollar     
`ZAR` | South Africa Rand        

The `--base` option is case-insensitive, and defaults to `USD`.  


Windows Usage
-------------
`cdash` uses ANSI escape sequences for colorization. Windows users must take
note to use a compatible shell.


[Releases]: https://github.com/chrisallenlane/cdash/releases/
[base]:     https://en.wikipedia.org/wiki/Currency_pair#Base_currency
[cmc]:      https://coinmarketcap.com/
[img]:      ./.github/screen.jpg
[issue-4]:  https://github.com/chrisallenlane/cdash/issues/4
