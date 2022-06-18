<script>
  // export let name;
  let firstName = "Jomphop";
  let lastName = "Saibuatong";
  let color = "red";
  let showText = false;
  let users = [
    { id: "1", name: "Gunt" },
    { id: "2", name: "Junior" },
    { id: "3", name: "Nerd" },
  ];

  $: name = `${firstName} ${lastName}`; // reactive value

  const toggle = () => {
    color = color === "red" ? "blue" : "red";
    showText = !showText;
    users = [...users, { id: "4", name: "Daimonsd" }];
  };
</script>

<main>
  <h1 style="color: {color}">Hello {name}!</h1>
  <!-- conditional render -->
  {#if showText}
    <p>
      Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn
      how to build Svelte apps.
    </p>
  {:else}
    <p>No Text</p>
  {/if}

  <!-- loop render -->
  {#each users as user (user.id)}
    <h3>{user.id}: {user.name}</h3>
  {/each}

  <button on:click={toggle}>Click</button>
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
