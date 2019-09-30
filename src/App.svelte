<script>
  export let name;
  import Hello from "./Components/Hello.svelte";
</script>

<style>
  h1 {
    color: purple;
  }
</style>

<div>
  <h1>Hello {name}!</h1>
  <Hello />
</div>
