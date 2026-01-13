<script>
  document.title = "jssvelte - color picker";
  import Slider from "./components/Slider.svelte";
  export let red = 0;
  export let green = 0;
  export let blue = 0;  
  let d2h = (value) => {
    return value.toString(16).padStart(2,'0');
  };  
</script>

<section>

  <h1>ColorSlider</h1>

  <p>use the sliders to mix a color</p>

  <p>re-usable slider component and reactive variables to print out rgb/hex values</p>

  <div class="sliders">    
    <p>red: <Slider color="red" bind:intensity={red} /></p>
    <p>green: <Slider color="green" bind:intensity={green} /></p>
    <p>blue: <Slider color="blue" bind:intensity={blue} /></p>    
  </div>

  <div class="rectangle" style="background: rgb({red},{green},{blue}"></div>
  <div class="rgb-code">rgb({red},{green},{blue})</div>
  <div class="hex-code">hex: #{d2h(red)}{d2h(green)}{d2h(blue)}</div>

</section>

<style>
  section {    
    width: 100%;
    margin: 0 auto;
  }

  .sliders {
    display: grid;
    grid-template-columns: auto auto auto;
    gap: 20px;    
  }

  .sliders p {
    display: flex;
    gap: 10px;
  }

  .rectangle {  
    height: 200px;
    width: 100%;
  }

  .rgb-code, .hex-code {
    font-size: 24pt;
    margin-top: 10px;
    text-align: center;
  }
</style>