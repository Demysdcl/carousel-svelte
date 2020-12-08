<script>
  export let direction = 'right'
</script>

<span class={`arrow ${direction}`} on:click />

<!-- markup (zero or more items) goes here -->
<style>
  .arrow {
    position: absolute;
    cursor: pointer;
    display: block;
    opacity: 0;
    height: 50px;
    width: 50px;
    background-color: #2f2f2f;
    border-radius: 50%;
    transition: all 0.6s;
  }

  .arrow::after {
    content: '';
    display: block;
    border-left: 4px solid #fff;
    border-bottom: 4px solid #fff;
    height: 20px;
    width: 20px;
    margin-top: 12px;
  }

  .left {
    left: 15px;
  }

  .left::after {
    margin-left: 17.5px;
    transform: rotate(45deg);
  }

  .right {
    right: 15px;
  }

  .right::after {
    margin-left: 7.5px;
    transform: rotate(-135deg);
  }
</style>
