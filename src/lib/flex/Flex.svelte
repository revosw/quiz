<script lang="ts">
  export let direction: "row" | "column";
  export let align: "start" | "center" | "end" | "stretch" = "stretch";
  export let justify: "start" | "center" | "end" | "stretch" = "stretch";
  export let gap: "loose" | "tight" = "tight";
</script>

<div
  style="
  flex-direction: {direction};
  justify-content: {justify};
  align-items: {align};
  gap: var(--{gap})"
>
  <slot />
</div>

<style>
  div {
    --loose: 48px;
    --tight: 24px;
    display: flex;
  }
  div > * {
    flex-shrink: 0;
  }
</style>
