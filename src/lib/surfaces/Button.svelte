<script lang="ts">
  export let color: "green"|"red" = "green"
  export let click: () => any
</script>

<style>
  button {
    padding: 15px 30px;
    font-size: 1.4rem;
    border-radius: var(--border-radius);
    border: var(--border);
    box-shadow: var(--shadow);
    cursor: pointer;
  }
</style>

<button style="background-color: var(--{color})" on:click={click}>
  <slot></slot>
</button>