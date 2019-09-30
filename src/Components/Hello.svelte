<script>
  let name = "world";
  let count = 0;

  const handleCount = () => {
    count += 1;
  };
</script>

<style>
  .helloworld {
    color: blue;
  }
</style>

<div>
  <p>You Have Clicked {count} {count === 1 ? 'time' : 'times'}!</p>
  <button class="helloworld" on:click={handleCount}>Click Me!</button>
</div>
