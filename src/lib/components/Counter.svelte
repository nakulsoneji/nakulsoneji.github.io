<script lang="ts">
  let count = 0;
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

<div class="red" style="width: 100px; text-align: center;">
  <button on:click={increment}>+</button>
  <br>
  {count}
  <br>
  <button on:click={decrement}>-</button>
</div>