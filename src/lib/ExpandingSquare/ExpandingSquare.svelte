<script>    
  export let size = 1
  export let minSize = size
  export let maxSize = 400  
  export let bgco = "red"
  export let interval = 50
  
  if (minSize > maxSize) {
    minSize = maxSize / 2
  }

  setInterval(() => {
    if (size === maxSize) {
      size = minSize
    }
    size += 1
  }, interval);
</script>

<h1>ExpandingSquare</h1>

<p>Uses a "setInterval" to grow the size of the square, then resets when it gets too big</p>

<div style="height: {size}px; width: {size}px; background: {bgco}"></div>