<script lang="ts">
  import type { Icon } from "src/types/types";

  export let color: "cyan"|"teal"|"green"|"red" = "cyan"
  export let padding: "tight"|"loose"|"none" = "tight"
</script>

<style>
  div {
    display: flex;
    /* justify-content: center; */

    border-radius: var(--border-radius);
    border: var(--border);
    box-shadow: var(--shadow);
    overflow: hidden;
    
  }
</style>

<div style="background-color: var(--{color}); padding: var(--{padding}); gap: var(--{padding})">
  <slot></slot>
</div>