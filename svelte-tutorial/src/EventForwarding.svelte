<script>
  import Button from "./components/Button.svelte";

  const log = () => {
    console.log("button clicked!");
  };
</script>

<main>
  <h1>Event Forwarding</h1>
  <!-- event forwarding => event ที่เกิดที่ child component จะ forwarding มาที่ parent  -->
  <!-- ตัวอย่าง Button event forwarding on:click กลับมาที่ parent โดย call log function ของ parent  -->
  <Button on:click={log} />
  <!-- event modifier 
    once => trigger event แค่ครั้งเดียวเท่านั้น
    self => trigger event เฉพาะ target element ที่ bind event เท่านั้น
    preventDefault => ไม่มีการ refresh หน้าถ้ามีการ submit
  -->
  <button on:click|once={log}>App Button</button>
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
</style>
