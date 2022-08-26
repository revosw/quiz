<script lang="ts">
  import Surface from "./Surface.svelte";
  export let placeholder: string;
</script>

<style>
  input {
    width: 100%;
    height: 100%;
  }
</style>

<Surface color="teal">
  <input {placeholder}>
</Surface>