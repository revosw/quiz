<script lang="ts">
  import Surface from "./Surface.svelte";
  export let placeholder: string;
  export let type: "single" | "multi" = "single";
  export let rows: '2' | '6' = '2'
</script>

<Surface padding='none' color="teal">
  {#if type === "single"}
    <input {placeholder} />
  {:else}
    <textarea rows={parseInt(rows)} {placeholder} />
  {/if}
</Surface>

<style>
  input,
  textarea {
    min-width: 150px;
    font-size: 1.1rem;
    color: white;
    width: 100%;
    height: 100%;
    appearance: none;
    border: unset;
    background: unset;
    outline: unset;
    padding: 10px;
  }

  textarea {
    resize: none;
  }

  ::placeholder {
    mix-blend-mode: multiply;
    /* color: var(--green); */
  }
</style>
