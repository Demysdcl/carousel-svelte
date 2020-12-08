<script>
  import Carousel from './container/Carousel.svelte'

  let images = [
    'img/image-1.jpg',
    'img/image-2.jpg',
    'img/image-3.jpg',
    'img/image-4.jpg',
  ]
</script>

<main>
  <Carousel {images} />
</main>
