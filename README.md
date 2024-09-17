
![logo](logo.png)

## Features

- Bypass CORS even when used locally.
- Connecting directly to the CRP.is API.

### Who is this solution for:

- If you want to build a web application that works with the API of the anonymous exchange CRP.is
- If you want to improve your API skills.
- When you create your own trading bot or trading terminal.
- If you are building a WEB3 application that requires stock exchange data.
- When you create your own service that accepts payments in Crypton or UUSD.
- When you create your own crypto exchange.

## Use from CDN

URL: `https://cdn.jsdelivr.net/gh/Sagleft/uexchange-js@v1.1.0/crypton-api.js`

```
<script src="https://cdn.jsdelivr.net/gh/Sagleft/uexchange-js@v1.1.0/crypton-api.js"></script>
```

![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E)

## Usage example

```js
const API = new CryptonAPI(transport, saveToken);
const response = await API.pairs();
console.log(response);
```

or

```js
// Wrap all the code in an async function
async function getRate() {
    const API = new CryptonAPI(transport, saveToken);
    try {
        const response = await API.pairs(); // Waiting for response from API
        const pairs = response.pairs;
        const crpUsdtPair = pairs.find(pair => pair.pair.pair === 'crp_usdt');

        if (crpUsdtPair) {
            const closePrice = crpUsdtPair.data_market.close;
            console.log('CRP/USDT rate is', closePrice);
        } else {
            console.log('Pair crp_usdt not found.');
        }
    } catch (error) {
        console.error('Error while getting pairs:', error);
    }
}

// Run the main function
getRate();
```

result:

```
CRP/USDT rate is 0.598
```

---

<a href="https://udocs.gitbook.io/utopia-api/">
  <img align="center" height="58" src="https://github.com/Sagleft/ures/blob/master/udocs-btn.png?raw=true">
</a>

<a href="https://utopia.im/RUTECH">
  <img align="center" height="58" src="https://github.com/Sagleft/ures/blob/master/rutopia_tech.png?raw=true">
</a>

<a href="https://talk.u.is">
  <img align="center" height="58" src="https://github.com/Sagleft/ures/blob/master/utalk.png?raw=true">
</a>

<a href="https://crp.is">
  <img align="center" height="58" src="https://github.com/Sagleft/ures/blob/master/crp_is.png?raw=true">
</a>
