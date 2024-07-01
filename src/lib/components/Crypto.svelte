<script>
    import { onMount } from 'svelte';
  
    /**
     * @type {{ symbol: any; price: any; }}
     */
    let cryptoData;
  
    const fetchCryptoData = async () => {
      try {
        const response = await fetch('https://api.coingecko.com/api/v3/simple/price?ids=bitcoin&vs_currencies=usd');
        if (!response.ok) {
          throw new Error('Crypto data not available');
        }
        const data = await response.json();
        cryptoData = {
          symbol: 'BTC',
          price: data.bitcoin.usd
        };
      } catch (error) {
        // @ts-ignore
        console.error('Error fetching crypto data:', error.message);
      }
    };
  
    onMount(fetchCryptoData);
  </script>
  
  <div class="crypto-app">
    {#if cryptoData}
      <div class="crypto">
        <div class="symbol">{cryptoData.symbol}</div>
        <div class="price">${cryptoData.price}</div>
      </div>
    {:else}
      <p>Loading...</p>
    {/if}
  </div>
  
  <style>
    .crypto-app {
      font-family: Arial, sans-serif;
      text-align: center;
      max-width: 300px;
      margin: 0 auto;
    }
  
    .crypto {
      display: flex;
      flex-direction: column;
      align-items: center;
    }
  
    .symbol {
      font-size: 2rem;
      font-weight: bold;
      margin: 10px 0;
    }
  
    .price {
      font-size: 1.5rem;
      margin: 5px 0;
    }
  </style>
  