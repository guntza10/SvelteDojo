<script>
  // import Announcement from "./components/Announcement.svelte";
  import Alert from "./components/Announcement.svelte"; // ตั้งชื่อ component ว่าอะไรก็ได้ แต่ best practice ควรตั้งให้ตรงกับชื่อไฟล์ component
</script>

<main>
  <h1>Components</h1>
  <!-- <Announcement /> -->
  <Alert />
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
