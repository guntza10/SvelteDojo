<script>
  import Form from "./components/Form.svelte";

  let foods = [
    { id: 1, name: "Apple", color: "red" },
    { id: 2, name: "Carrot", color: "orange" },
  ];

  const addFood = (event) => {
    const food = event.detail;
    // สาเหตุที่ใช้ท่านี้แทนการ push เพราะว่า ui จะ re-render ก็ต่อเมื่อ variable มีการ re-assigned ซึ่งการ push foods มีการอัพเดทค่าจริง แต่ไม่ใช่การ re-assigned ทำให้ ui จะไม่ re-render ใหม่
    foods = [food, ...foods];
  };
</script>

<main>
  <h1>Dispatching Custom Events</h1>
  <Form on:add-food={addFood} />
  {#each foods as food (food.id)}
    <div class="fooditem">
      <h3>{food.name}</h3>
      <p>color: {food.color}</p>
    </div>
  {/each}
</main>

<style>
  .fooditem {
    border: 2px solid gray;
    text-align: left;
    padding: 8px;
    margin-top: 20px;
    width: 80%;
  }

  main {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
  }

  h1 {
    font-size: 72px;
  }
</style>
