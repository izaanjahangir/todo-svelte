<script>
  export let color = "",
    onClick;
  import Ripple from "@smui/ripple";
</script>

<button
  on:click={onClick}
  use:Ripple={{ surface: true }}
  class={`button ${color}`}
>
  <slot />
</button>

<style>
  .button {
    border-width: 0;
    color: white;
    padding: 5px 20px;
    border-radius: 5px;
    cursor: pointer;
  }

  .red {
    background-color: red;
  }
</style>
