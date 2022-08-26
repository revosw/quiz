<script lang="ts">
  import Surface from "./Surface.svelte";
  export let placeholder: string;
  export let type: "single" | "multi" = "single";
  export let rows: "2" | "6" = "2";
  export let value: string;
</script>

<Surface padding="none" color="teal">
  {#if type === "single"}
    <input {value} {placeholder} {...$$restProps} />
  {:else}
    <textarea {value} {placeholder} rows={parseInt(rows)} {...$$restProps} />
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

  ::-webkit-scrollbar {
    display: none;
  }
</style>
