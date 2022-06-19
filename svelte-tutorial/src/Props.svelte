<script>
  import Button from "./components/Button.svelte";
</script>

<main>
  <h1>Props</h1>
  <!-- props -->
  <Button btnText="click it!" />
  <!-- default -->
  <Button />
</main>

<style>
  main {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  h1 {
    font-size: 72px;
  }
</style>
