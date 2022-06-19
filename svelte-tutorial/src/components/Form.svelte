<script>
  import { createEventDispatcher } from "svelte";
  let name;
  let color;

  const dispatch = createEventDispatcher();

  const handleSubmit = () => {
    const food = {
      id: Math.random(),
      name: name,
      color: color,
    };

    dispatch("add-food", food);

    name = "";
    color = "";
  };
</script>

<form on:submit|preventDefault={handleSubmit}>
  <input type="text" placeholder="name" bind:value={name} />
  <input type="text" placeholder="color" bind:value={color} />
  <button>Add Food</button>
</form>

<style></style>
