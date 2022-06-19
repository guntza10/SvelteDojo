<script>
  // props default define value
  export let btnText = "Component Button";
  // props default not define=>undefine
  //   export let btnText;
</script>

<!-- event forwarding -->
<button on:click>{btnText}</button>

<style>
  button {
    background: #667eea;
    border: 1px solid #4c51bf;
    color: #fff;
  }
</style>
