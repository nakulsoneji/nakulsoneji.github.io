<script lang="ts">
  import {createEventDispatcher} from 'svelte';
  const dispatch = createEventDispatcher();


  export let text: string;
  export let done: boolean;
  export let id: number;
</script>

<style>
  .done {
    text-decoration: line-through;
  }
</style>

<div>
  <input type="checkbox" on:change={() => dispatch("toggle")}>
  <span class:done={done}>{text}</span>
  <button on:click={() => dispatch("delete")}>delete</button>
</div>