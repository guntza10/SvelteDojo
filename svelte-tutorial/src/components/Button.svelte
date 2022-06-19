<script>
  // props default define value
  export let btnText = "Component Button";
  // props default not define=>undefine
  //   export let btnText;
</script>

<!-- event forwarding -->
<!-- event modifier -->
<div class="card" on:click|self>
  <button>{btnText}</button>
</div>

<style>
  button {
    background: #667eea;
    border: 1px solid #4c51bf;
    color: #fff;
  }

  .card {
    padding: 12px;
    border: 2px solid gray;
    margin-bottom: 8px;
  }
</style>
