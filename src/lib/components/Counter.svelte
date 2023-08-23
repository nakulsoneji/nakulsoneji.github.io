<script lang="ts">
  let count = 0;
  let ms = 1000;
  const incr = () => (count += 1)

  let increment = () => {
    if (count >= 0) {
      count++;
    }
  }

  let decrement = () => {
    if (count > 0) {
      count--;
    }
  }
</script>

<div class="red" style="width: 100px; text-align: center; display: inline-flex; flex-direction: column; align-items: center;">
  <button style="width: 50px;" on:click={increment}>+</button>
  {count}
  <button style="width: 50px;" on:click={decrement}>-</button>
</div>
