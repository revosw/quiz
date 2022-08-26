<script lang="ts">
  export let color: "green"|"red" = "green"
  export let click: () => any
</script>

<style>
  button {
    aspect-ratio: 1;
    line-height: 0;
    font-size: 1.4rem;
    border-radius: 90px;
    border: var(--border);
    box-shadow: var(--shadow);
    cursor: pointer;
  }
</style>

<button style="background-color: var(--{color})" on:click={click}>
  <slot></slot>
</button>