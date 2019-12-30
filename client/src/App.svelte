<script>
  import { writable } from "svelte/store";

  let counter = writable(2);
  let array;
  $: array = [...Array($counter).keys()];
</script>

<style>
  main {
    width: 100%;
    height: 100%;

    display: flex;
    flex-direction: column;
  }

  .child {
    margin: 1px;
    color: white;
    text-align: center;
    background-color: black;
  }
</style>

<main>
  <input type="range" bind:value={$counter} />
  {#each array as item}
    <div class="child" style="flex: {item}">{item}</div>
  {/each}
</main>
