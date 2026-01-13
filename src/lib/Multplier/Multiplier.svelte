<script>    
  let original = 1;
  let multiplier = 1.13;
  let decimalPlaces = 2;
  // this variable derives its value reactively from other variables 
  $: product = original * multiplier;
</script>

<section>

  <h1>Multiplier</h1>

  <p>multiplies two numbers together reactively and truncates up to 8 decimal places</p>

  <p>handy for currency exchange rates or any other conversion calculators</p>

  <div class="flex">

    <div class="cell">

      <h2>original</h2>
      <input type="number" bind:value={original} />

      <h2>multiplier</h2>
      <input type="number" bind:value={multiplier} />

      <h2>decimal places</h2>
      <select bind:value={decimalPlaces}>
        <option value={0}>0</option>
        <option value={1}>1</option>
        <option value={2}>2</option>
        <option value={3}>3</option>
        <option value={4}>4</option>
        <option value={5}>5</option>
        <option value={6}>6</option>
        <option value={7}>7</option>
        <option value={8}>8</option>
      </select>

    </div>

    <div class="cell">

      <h2>product</h2>
      <input class="readonly" type="number" value={product.toFixed(decimalPlaces)} readonly />

    </div>

  </div>

</section>

<style>
  
  .flex {
    display: flex;
    gap: 50px;
    align-items: center;    
  }  
  
  input, select {
    font-size: 18px;
    margin-bottom: 15px;
    padding: 5px;
  }

  .readonly {
    background: #eee;
  }

</style>