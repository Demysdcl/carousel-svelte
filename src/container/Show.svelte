<script>
  import { fly } from 'svelte/transition'

  export let condition = false
</script>

{#if condition}
  <div
    on:click
    in:fly={{ duration: 300, x: 20 }}
    out:fly={{ duration: 300, x: -20 }}>
    <slot />
  </div>
{/if}

<style>
  div {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
  }
</style>
