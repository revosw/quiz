<script lang="ts">
  import type { Icon } from "src/types/types";

  export let color: 'cyan'|'teal'|'green'|'red' = 'cyan'
  export let padding: 'tight'|'loose' = 'tight'
</script>

<style>
  div {
    display: flex;
    /* justify-content: center; */

    border-radius: var(--border-radius);
    border: var(--border);
    box-shadow: var(--shadow);
  }
</style>

<div style="background-color: var(--{color}); padding: var(--{padding}); gap: var(--{padding})">
  <slot></slot>
</div>