<script>
  import './app.css';
  import * as Components from "./lib";
  export let initial = 'ColorPicker';

  // get component names from lib folder
  const names = Object.keys(Components);

  // show `initial` component, otherwise use the first available name
  let currentName = names.includes(initial) ? initial : (names[0] ?? initial);
  $: Current = Components[currentName];

  // functions to navigate through the components

  function prev() {
    const i = names.indexOf(currentName);
    currentName = names[(i - 1 + names.length) % names.length];
  }

  function next() {
    const i = names.indexOf(currentName);
    currentName = names[(i + 1) % names.length];
  }

</script>

<main>

  <div class="controls">

    <h1> JSsvelte </h1>
    
    <p> a Svelte playground by @joncoded </p>

    <!-- component navigation -->  

    <select bind:value={currentName} aria-label="Choose component">
      {#each names as name}
        <option value={name}>{name}</option>
      {/each}
    </select>

    <button on:click={prev} disabled={names.length <= 1}>previous app</button>

    <button on:click={next} disabled={names.length <= 1}>next app</button>

  </div>

  <!-- component display -->

  <div class="display">

    {#if Current}
      <svelte:component this={Current} />
    {:else}
      <p>No component found for <code>{currentName}</code></p>
    {/if}

  </div>

</main>

<style>

  main {
    padding: 15px;  
  }

  h1 {
    color: #000;
    margin-bottom: -15px;
  }

  .controls {
    margin: 15px 0;
  }

  button {
    font-size: 16pt;
    padding: 5px 10px;
    margin: 0 5px;
  }

  select {
    font-size: 16pt;
    padding: 5px;
    margin: 0 10px 0 0;
  }

  .display {    
    margin: 15px 0;          
  }
</style>