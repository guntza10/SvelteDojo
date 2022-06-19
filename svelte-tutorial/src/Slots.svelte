<script>
  import Card from "./components/Card.svelte";
</script>

<main>
  <h1>Slots</h1>
  <!-- slot => คือการเอา content ภายใน closing tag ของ component ที่เราสร้างไป render ผ่าน tag slots -->
  <!-- จากตัวอย่างเราเอา content ภายใน Tag Card component ของเราไป render ผ่าน tag slot ที่ component Card -->
  <!-- ก็เหมือนการเอา children ของ component ไป render เหมือนใน reactJs  -->
  <Card>
    <h3>Card</h3>
    <p>This is our card</p>

    <!-- <button>Test Button From Slot</button> -->
    <!-- เป็นการ define element ให้เป็น slot โดยการตั้งชื่อ slot แล้วเอาไป render ต่อที่ component -->
    <button slot="buttonSlot">Test Button From Slot</button>

    <h4>This is below everything</h4>
  </Card>
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
