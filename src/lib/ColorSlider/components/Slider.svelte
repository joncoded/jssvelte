<script>
  export let color;
  export let intensity = 0;
</script>

<input style="accent-color: {color}" type="range" min="0" max="255" bind:value={intensity} />

<style>
  input {
    width: 100%;
  }
</style>