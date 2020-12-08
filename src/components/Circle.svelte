<script>
  export let active = false
</script>

<span class="circle" class:active />

<style>
  .circle {
    display: block;
    background-color: #fff;
    border: 0.5px solid #252525;
    width: 12px;
    height: 12px;
    border-radius: 50%;
    opacity: 0.7;
    margin: 0px 10px;
  }

  .active {
    opacity: 1;
  }
</style>
