<script lang="ts">
  import Surface from "./Surface.svelte";
  export let placeholder: string;
</script>

<style>
  input {
    font-size: 1.1rem;
    color: white;
    width: 100%;
    height: 100%;
    appearance: none;
    border: unset;
    background: unset;
    outline: unset;
  }

  ::placeholder {
    mix-blend-mode: multiply;
    /* color: var(--green); */
  }
</style>

<Surface color="teal">
  <input {placeholder}>
</Surface>