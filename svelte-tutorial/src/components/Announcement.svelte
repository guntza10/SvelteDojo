<script>
  let show = true;
  let warning = false;

  const hideAlert = () => {
    show = false;
  };
</script>

{#if show}
  <!-- css & class directive -->
  <!-- css ที่ถูกเขียนใน component จะใช้ได้แค่ใน component นั้นๆเท่านั้น ถ้าอยากให้ใช้ได้ทุก component ให้ไปเขียนที่ global.css -->
  <!-- class directive => class:ชื่อ class ={true/false} -->
  <!-- <div class="alert" class:warning={warning}> -->
  <!-- shorthand class directive ถ้ามันชื่อเดียวกับตัวแปรที่เราเอามา bind -->
  <div class="alert" class:warning>
    50 % off all fruit. sign up for more fruit!
    <button on:click={hideAlert}>Hide</button>
  </div>
{/if}

<style>
  .alert {
    padding: 8px;
    font-size: 18px;
    background-color: darkgreen;
    color: darkslategray;
  }

  .warning {
    background-color: lightpink;
    color: darkred;
  }
</style>
