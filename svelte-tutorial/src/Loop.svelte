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
</script>

<main>
  <h1>Loop</h1>
  {#each fruits as fruit (fruit.id)}
    <div class="card">
      <h5>{fruit.name}</h5>
      <p>{fruit.color}</p>
    </div>
    <!-- if array empty -->
  {:else}
    <p>There is no fruit in our fruit array</p>
    <p>There is no fruit in our fruit array2</p>
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
  h1 {
    font-size: 38px;
  }
</style>
