<script lang="ts">
  import Flex from "./Flex.svelte";
  export let align: "start" | "center" | "end" | "stretch" = "stretch";
  export let justify: "start" | "center" | "end" | "stretch" = "stretch";
  export let gap: "loose" | "tight" = "tight";
</script>

<Flex direction="column" {align} {justify} {gap}>
  <slot />
</Flex>
