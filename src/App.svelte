<script>
  export let name;
  import Colors from "./Components/Colors.svelte";
</script>

<style>
  h1 {
    color: purple;
  }
</style>

<div>
  <h1>Hello {name}!</h1>
  <Colors />
</div>
