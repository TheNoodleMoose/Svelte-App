<script>
  let name = "world";
  let count = 0;
  let colors = [];
  let savedColors = [];
  let savedCount = 5;

  const handleCount = () => {
    count += 1;
  };

  const GetColors = () => {
    if (savedCount > 0) {
      fetch(`https://api.noopschallenge.com/hexbot?count=${savedCount}`, {
        method: "GET", // *GET, POST, PUT, DELETE, etc.
        mode: "cors", // no-cors, cors, *same-origin
        cache: "no-cache", // *default, no-cache, reload, force-cache, only-if-cached
        credentials: "same-origin", // include, *same-origin, omit
        headers: {
          "Content-Type": "application/json"
          // "Content-Type": "application/x-www-form-urlencoded",
        },
        redirect: "follow", // manual, *follow, error
        referrer: "no-referrer" // no-referrer, *client
      })
        .then(response => response.json())
        .then(res => {
          colors = res.colors;
        });
    }
  };
</script>

<style>
  .helloworld {
    color: blue;
  }

  .color-block {
    width: 100px;
    height: 100px;
  }
</style>

<div>
  <p>You Have Clicked {count} {count === 1 ? 'time' : 'times'}!</p>
  <button class="helloworld" on:click={handleCount}>Click Me!</button>
  <button on:click={GetColors}>Get Colors!</button>
  {#each colors as color}
    <div
      class="color-block"
      style="background-color: {color.value}; color: white">
      {color.value}
    </div>
  {/each}
</div>
