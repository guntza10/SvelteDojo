<script>
  let name = "Gunt";
  let src = "favicon.png";
  let count = 0;

  const incrementCounter = () => {
    count += 1;
  };
</script>

<main>
  <h1>Variables and Styling</h1>
  <h2>Hello {name}</h2>
  <h3>Counter: {count}</h3>
  <button on:click={incrementCounter}>Add 1 to Counter</button>
  <!-- shorthand -->
  <img {src} alt="svelte logo" />
  <!-- <img src= {src} alt="svelte logo" /> -->
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
  h3 {
    font-size: 38px;
  }
</style>
