<script>
  let firstName = "";
  let lastName = "";

  //   reactive value => ถ้าเรามีการ update value อะไรก็ตามที่ bind กับ reactive value ตัว reactive value จะ re-update ตัวเอง
  //   เช่น ถ้า firstName หรือ lastName มีการ update value ตัว fullName ที่เป็น reactive value ก็จะ re-update ด้วย
  //  reactive value มันจะ run every time ที่ value ที่ bind กับ reactive มีการ update
  $: fullName = `${firstName} ${lastName}`;
  // reactive one line
  $: console.log(lastName);
  // reactive multiple line
  $: {
    console.log(firstName);
    console.log(lastName);
  }
</script>

<main>
  <h1>Reactive Values</h1>
  <h2>Hello {fullName}</h2>
  <label for="firstName">FirstName</label>
  <input type="text" bind:value={firstName} />
  <label for="lastName">lastName</label>
  <input type="text" bind:value={lastName} />
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
