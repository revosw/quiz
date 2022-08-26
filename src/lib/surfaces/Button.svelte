<script lang="ts">
  import Surface from "./Surface.svelte";
</script>

<Surface padding='loose' on:click={() => console.log("hello")} color="green">
  <slot></slot>
</Surface>