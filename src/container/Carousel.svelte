<script>
  import { onMount } from 'svelte'
  import Arrow from '../components/Arrow.svelte'
  import Circle from '../components/Circle.svelte'
  import Show from './Show.svelte'

  export let images = []

  let currentIndex = 0

  const handlePreviews = () => {
    currentIndex === 0 ? (currentIndex = 3) : currentIndex--
  }

  const handleNext = () => {
    currentIndex === images.length - 1 ? (currentIndex = 0) : currentIndex++
  }

  onMount(() => {
    setInterval(handleNext, 3000)
    return clearInterval(handleNext)
  })
</script>

<div class="carousel">
  <Arrow direction="left" on:click={handlePreviews} />

  {#each images as item, i}
    <Show condition={currentIndex === i}>
      <div class="image-container"><img src={item} alt={`image-${i}`} /></div>
    </Show>
  {:else}Empty list{/each}

  <Arrow on:click={handleNext} />

  <footer>
    {#each images as _, i}
      <Circle active={currentIndex === i} />
    {/each}
  </footer>
</div>

<style>
  .carousel {
    position: relative;
    height: 500px;
    width: 80vw;
    margin: 0 auto;
    display: flex;
    align-items: center;
    background-color: #2f2f2f;
  }

  .carousel:hover :global(.arrow) {
    opacity: 1;
  }

  .image-container {
    width: 100%;
    height: 100%;
  }

  img {
    height: 100%;
    display: block;
    margin: 0 auto;
  }

  footer {
    position: absolute;
    width: 100%;
    bottom: 10px;
    display: flex;
    justify-content: center;
  }
</style>
