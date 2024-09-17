
![logo](logo.png)

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
