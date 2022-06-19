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
  <!-- two-way binding -->
  <input type="text" bind:value={name} />
  <!-- one-way binding => ถ้า name มีการเปลี่ยน input ตัวนี้ก็จะเปลี่ยนตาม แต่ถ้า input เปลี่ยน name ไม่ได้เปลี่ยนด้วย -->
  <input type="text" value={name} />
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
  h3 {
    font-size: 38px;
  }
</style>
