<script>
  let name = 'Default';
  let fontSize = 12;
  let min = 10;
  let max = 128;
</script>

<section>

  <h1>FontSlider</h1>

  <p>visualize the font size that reacts with a slider</p>

  <label for="fontSize">{min}px font</label>
  <input name="fontSize" type="range" bind:value={fontSize} min={min} max={max}/>
  <label for="fontSize">{max}px font</label>

  <p style="margin: 10px 0; font-size: {fontSize}px">font size is now: {fontSize}px</p>

</section>