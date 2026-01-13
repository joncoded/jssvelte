<script>
  let top = 0
  let left = 0

  function onInput(e) {
    console.log(e.target.value, 'input')
  }
  function onChange(e) {
    console.log(e, 'change')
  }
  function onKeyup(e) {
    console.log(e.key, e, 'keypressed')    
    switch (e.key) {
      case 'ArrowLeft':
        left -= 10
        break
      case 'ArrowRight':
        left += 10
        break
      case 'ArrowUp':
        top -= 10
        break
      case 'ArrowDown':
        top += 10
        break
      
    }
  }
  function handleSubmit(e) {    
    console.log('submitting')
  }
</script>

<!-- key bindings (svelte will note keypresses in onKeyup) -->

<h1>KeyEventSquare</h1>

<p>Use the keyboard arrow keys to move the square</p>

<svelte:window on:keyup={onKeyup} />

<!-- moving box based on key events -->
<div id="box" class="box" style="top: {top}px; left: {left}px"></div>

<style>
  .box { background: #000; height: 100px; width: 100px; margin-top: 10px; position: relative; }
</style>