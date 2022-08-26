<script lang="ts">
  import type { Icon } from "src/types/types";
  export let icon: Icon;
</script>

<style>
  img {
    width: 24px;
    height: 24px;
  }
</style>

<img src="src/assets/icons/{icon}.svg" alt="" />
