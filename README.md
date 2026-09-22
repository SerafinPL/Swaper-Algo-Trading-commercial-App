# Swaper Algo Trading Commercial App

Algo trading bot with Risk-reward management. Swaping crypto on various exchanges by REST api.
##

### 🛠️ Stack: 

![Static Badge](https://img.shields.io/badge/linux-mint-xfce?style=plastic&logo=linuxmint)
![Static Badge](https://img.shields.io/badge/git_at_-github-ex?style=plastic&logo=git&logoColor=F05032&color=F05032)

![Static Badge](https://img.shields.io/badge/nodejs-22.20.0-ex?style=plastic&logo=nodedotjs)
![Static Badge](https://img.shields.io/badge/typescript-5.8.3-ex?style=plastic&logo=typescript&logoColor=3178C6&color=3178C6)
![Static Badge](https://img.shields.io/badge/axios-1.10.0-ex?style=plastic&logo=axios&logoColor=%235A29E4&color=%235A29E4)

![Static Badge](https://img.shields.io/badge/dotenv-16.5.0-ex?style=plastic&logo=dotenv&color=%23ECD53F)
![Static Badge](https://img.shields.io/badge/express.js-5.1.0-ex?style=plastic&logo=express&labelColor=%23000&color=%23fff)
![Static Badge](https://img.shields.io/badge/mongodb-6.17.0-ex?style=plastic&logo=mongodb&labelColor=%23000&color=%23fff)
##

### 🏦 Exchanges: 

algoTrade & manual purchase with invest tracking + RRM integration:

![Static Badge](https://img.shields.io/badge/kucoin-api-ex?style=plastic&logo=kucoin&labelColor=%23000&color=%2301BC8D) 

![Static Badge](https://img.shields.io/badge/kraken-api-ex?style=plastic&labelColor=%235841D8&color=%23000)

The previous AlgoTrade and manual purchase integration with investment tracking and RRM is currently unsupported:
![Static Badge](https://img.shields.io/badge/binance-api-ex?style=plastic&logo=binance&logoColor=%23F0B90B&labelColor=%23000&color=%23F0B90B)

##

### Features

- **Risk & Reward management algorithm** - The implemented strategy calculates the profit/loss of a position relative to the total capital and the overall profit/loss of the capital. The algorithm compares the defined levels of accepted risk and reward relative to the position and capital. On this basis, it makes independent decisions about the possible exit from a particular position or the entire investment.
- Trading algos:
  - **A purchasing algorithm** based on three indicators calculated using data from the various exchanges. Thanks to the implemented indicator analysis, it makes independent decisions regarding purchases and purchase volumes. The algorithm is executed cyclically according to a set number of hours.
  - **The selling algorithm** is based on a comparison of investment values taken from the database and current market data. The algorithm analyzes the current value of individual investments, and those that generate a profit of x*% or higher are processed further. For selected positions, the algorithm saves the “highest profit” in the database. In subsequent cycles, it sells positions after reaching x*% of the ‘highest profit’ value or raises the ‘highest profit’ value. The algorithm is executed cyclically according to a set number of minutes. It works similarly to a raising stop-loss order.
- REST API communication with: Binance, Kraken, KuCoin.
- API to communicate with client app.
- MongoDB communication

[ x* ] - x is a ingteger
##

 ![Logo](https://kubakoder.pl/_next/image?url=%2F_next%2Fstatic%2Fmedia%2Ffavicon.5d6e1adf.png&w=48&q=75)

### 👨🏻‍💻 Author: [@SerafinPL](https://www.github.com/serafinpl)

### 🌐 Author URI: [http://kubakoder.pl](http://kubakoder.pl)
##

### Roadmap

**on plan to do:**

- [ ] remake invest data structure and workflow to work with more than one user
- [ ] ![Static Badge](https://img.shields.io/badge/okx-api-ex?style=plastic&logo=okx&labelColor=%23000000&color=%23ffffff) integration
   
**in progress:**

**Ver 0.10 – Clever Grid Algorithm – Q4 2026 (In Progress)**

[ ] Developing a new non-predictive algorithm, tentatively named "Clever Grid," that combines Dollar Cost Averaging (DCA) and Grid Trading techniques.

**done:**

**Ver 0.9 – Spot Trading & Kraken Futures Predictive Algorithm – Q3 2026**


[x] A completely new indicator-based predictive algorithm was developed to replace the legacy system on ![Static Badge](https://img.shields.io/badge/kraken-api-ex?style=plastic&labelColor=%235841D8&color=%23000).  Futures trading was integrated to generate profits from both long and short positions during bullish and bearish trends. Additionally, a risk-reward system was implemented within this solution to automatically place orders with corresponding take-profit and stop-loss levels.

[x] The legacy algorithm was disabled on ![Static Badge](https://img.shields.io/badge/kraken-api-ex?style=plastic&labelColor=%235841D8&color=%23000), and all Binance exchange support functionality was completely removed from the application.

[x] CoinGecko API integration was implemented to fetch indicators for the new decision-making algorithm from the broader cryptocurrency market, eliminating reliance on data from a single exchange.

[x] The legacy algorithm's trading execution ![Static Badge](https://img.shields.io/badge/kucoin-api-ex?style=plastic&logo=kucoin&labelColor=%23000&color=%2301BC8D)  was refactored from Convert services to Spot trading to reduce transaction fees.

---

**Ver 0.8 – New Features & Migration of Purchasing Algorithm from Binance to KuCoin – Q2 2026**

* [x] The purchasing and selling algorithm was migrated from Binance to ![Static Badge](https://img.shields.io/badge/kucoin-api-ex?style=plastic&logo=kucoin&labelColor=%23000&color=%2301BC8D)  due to Binance's withdrawal from European operations following the introduction of MiCA regulations.
* [x] A selling algorithm with time cycles on ![Static Badge](https://img.shields.io/badge/kucoin-api-ex?style=plastic&logo=kucoin&labelColor=%23000&color=%2301BC8D)  was implemented.
* [x] An API was developed to enable purchases on ![Static Badge](https://img.shields.io/badge/kucoin-api-ex?style=plastic&logo=kucoin&labelColor=%23000&color=%2301BC8D)  via the client application.
* [x] An API was created to retrieve investment and ![Static Badge](https://img.shields.io/badge/kucoin-api-ex?style=plastic&logo=kucoin&labelColor=%23000&color=%2301BC8D)  data simultaneously for the client application.
* [x] ![Static Badge] Full-feature integration was enabled following new capabilities launched in the ![Static Badge](https://img.shields.io/badge/kucoin-api-ex?style=plastic&logo=kucoin&labelColor=%23000&color=%2301BC8D)  API.[Thanks to the functionality launched in the KuCoin API, we can create full integration.](https://www.kucoin.com/announcement/hk-kucoin-convert-now-supports-api-trading?lang=en_US) 
* [x] Front-end views were created to support on-demand purchasing and selling, wallet status monitoring, and algorithm performance tracking.
* [x] A new mode for saving and loading status in MongoDB was implemented, replacing a single global object with individual purchase settings configured separately for each coin.
* [x] The ability to sell cryptocurrencies was added on the front end, supporting sales based on market price or an adjusted purchase price (DCA). Selling at market price realizes profit or loss without affecting the stored price, whereas selling based on purchase price allows the algorithm to dynamically modify the target price in memory.
* [x] A new, comprehensive backend error handling system was designed and implemented to manage all exceptions originating from various external APIs and the MongoDB database.

---

**Ver 0.7 – New Front-End Layout – Q1 2026**

* [x] The new front-end application was developed using Next.js version 15. The changes were aimed at integrating OAuth, improving table display, upgrading Next.js from version 14 along with related packages, and changing the UI framework from daisyUI to HeroUI.
* [x] OAuth integration was required to make the application available to beta testers.
* [x] NextAuth and MongoDB integration was implemented.

---

**Ver 0.6 – Migration to VPS – 2025**

* [x] The entire application code was reviewed.
* [x] Error handling was improved, and logs about issues were stored in the database.
* [x] Some modifications were required for the migration to a VPS.

---

**Ver 0.5 – Independent Trading App with Risk & Reward Management Mode – 2025**

* [x] The implementation of the connection with the Near protocol was removed.
* [x] A Risk & Reward management mode with time cycles on Binance was implemented.
* [x] A Risk & Reward management algorithm and its data structure were developed and implemented.

---

**Ver 0.4 – Independent Purchasing & Selling App – 2025**

* [x] A purchasing algorithm with time cycles on Binance was implemented.
* [x] Investment data was migrated from the Near Protocol to MongoDB.
* [x] Integration with a new database provider (MongoDB 6.17.0) was completed.
* [x] Complex assessment and indicator ranking algorithms were modified, and Price Trend was added to the calculations based on testing feedback.
* [x] Price Trend was calculated using candlestick (kline) data from ![Static Badge](https://img.shields.io/badge/kraken-api-ex?style=plastic&labelColor=%235841D8&color=%23000) and Binance.
* [x] Testing with live market data and backtesting of complex assessment and indicator ranking functions were conducted.
* [x] An API was developed to provide candlestick data along with calculated indicators and rankings from all three exchanges to the client application.
* [x] A complex assessment system based on three indicators was developed and implemented.
* [x] A ranking algorithm for “Indicator 3” calculations was developed and implemented.
* [x] “Indicator 3” was calculated using candlestick data from ![Static Badge](https://img.shields.io/badge/kraken-api-ex?style=plastic&labelColor=%235841D8&color=%23000) and Binance.
* [x] Two indicators were calculated using candlestick data from Binance.

---

**Ver 0.3 – Independent Enhanced Selling App – 2024**

* [x] The sales algorithm was extended with a “highest profit” stop-loss functionality.
* [x] A selling algorithm with time cycles on Binance was implemented.
* [x] Binance was added to the APIs.
* [x] Binance API integration was completed.
* [x] Ranking algorithms for “Indicator 2” and “Indicator 1” calculations were developed and implemented.
* [x] “Indicator 2” was calculated using candlestick data from ![Static Badge](https://img.shields.io/badge/kraken-api-ex?style=plastic&labelColor=%235841D8&color=%23000).
* [x] “Indicator 1” was calculated using candlestick data from ![Static Badge](https://img.shields.io/badge/kraken-api-ex?style=plastic&labelColor=%235841D8&color=%23000).
* [x] The API was expanded to enable purchases on more than one exchange through the client application.

---

**Ver 0.2 – Independent Selling App – 2024**

* [x] A selling algorithm with time cycles on ![Static Badge](https://img.shields.io/badge/kraken-api-ex?style=plastic&labelColor=%235841D8&color=%23000) was implemented.
* [x] A selling algorithm was developed and implemented.
* [x] The API was expanded to allow the client application to get and set investment data across multiple exchanges.
* [x] The investment data structure was redesigned to support multiple exchanges.
* [x] An API was created to retrieve investment and ![Static Badge](https://img.shields.io/badge/kucoin-api-ex?style=plastic&logo=kucoin&labelColor=%23000&color=%2301BC8D)  data simultaneously for the client application.
* [x] Read-only integration with the ![Static Badge](https://img.shields.io/badge/kucoin-api-ex?style=plastic&logo=kucoin&labelColor=%23000&color=%2301BC8D)  API was completed.
* [x] An API was developed to enable purchases on ![Static Badge](https://img.shields.io/badge/kraken-api-ex?style=plastic&labelColor=%235841D8&color=%23000) via the client application.
* [x] An API was created to retrieve investment and ![Static Badge](https://img.shields.io/badge/kraken-api-ex?style=plastic&labelColor=%235841D8&color=%23000) data simultaneously for the client application.
* [x] An API was developed to allow the client application to get and set investment data.

---

**Ver 0.1 – Initial Application Setup – 2024**

* [x] Near smart contract integration was implemented as the database solution.
* [x] ![Static Badge](https://img.shields.io/badge/kraken-api-ex?style=plastic&labelColor=%235841D8&color=%23000) API integration was completed.
* [x] The initial project configuration was set up using Node.js (v22.20.0), TypeScript (v5.8.3), and dotenv (v16.5.0).
