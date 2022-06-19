<script>
  let fruits = [
    {
      id: 1,
      name: "Apple",
      color: "red",
      amount: 5,
    },
    {
      id: 2,
      name: "Banana",
      color: "yellow",
      amount: 7,
    },
    {
      id: 3,
      name: "Grape",
      color: "purple",
      amount: 3,
    },
  ];

  const deleteFruit = (id) => {
    fruits = fruits.filter((it) => it.id !== id);
  };
</script>

<main>
  <h1>Inline Event Handlers</h1>
  {#each fruits as fruit (fruit.id)}
    <div class="card">
      <h5>{fruit.name}</h5>
      <p>{fruit.color}</p>
      <button on:click={() => deleteFruit(fruit.id)}>Delete Fruit</button>
    </div>
  {:else}
    <p>There is no fruit in our fruit array</p>
  {/each}
</main>

<style>
  .card {
    padding: 8px;
    border-radius: 20px;
    border: 2px solid gray;
    width: 500px;
    margin-bottom: 8px;
  }
  h5,
  p {
    margin: 4px 0;
  }
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
