<script>
  let name;
  let num;
  let isChecked = true;
  let value = 3;
  let selected;

  let questions = [
    { id: 1, text: "What is your favourite color?" },
    { id: 2, text: "What is your favourite fruit?" },
  ];
</script>

<main>
  <h1>Input Types</h1>
  <input type="text" bind:value={name} />
  <input type="number" bind:value={num} />
  <input type="checkbox" bind:checked={isChecked} />

  <div>
    <label>
      <input type="radio" bind:group={value} value={1} />
      1
    </label>
    <label>
      <input type="radio" bind:group={value} value={2} />
      2
    </label>
    <label>
      <input type="radio" bind:group={value} value={3} />
      3
    </label>
  </div>

  <select bind:value={selected}>
    {#each questions as question}
      <option value={question}>{question.text}</option>
    {/each}
  </select>
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
