<script lang="ts">
import type { FlexDistribution } from "src/types/types";

  import Flex from "./Flex.svelte";
  export let align: FlexDistribution = "stretch";
  export let justify: FlexDistribution = "stretch";
  export let gap: "loose" | "tight" = "tight";
</script>

<Flex direction="row" {align} {justify} {gap}>
  <slot />
</Flex>