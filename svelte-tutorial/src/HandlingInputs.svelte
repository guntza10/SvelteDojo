<script>
  let name = "";

  const handleInput = (event) => {
    name = event.target.value;
  };

  const resetName = (event) => {
    name = "Unknown";
  };
</script>

<main>
  <h1>Handling Inputs</h1>
  <h2>Hello {name}</h2>
  <!-- on:input เอาไว้ดักเวลา input มีการ change -->
  <input type="text" on:input={handleInput} />
  <!-- two-waybinding shorthand-->
  <input type="text" on:input={handleInput} bind:value={name} />
  <!-- two-waybinding -->
  <input type="text" on:input={handleInput} value={name} />
  <button on:click={resetName}>set name to Unknown</button>
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
  h1 {
    font-size: 38px;
  }
</style>
