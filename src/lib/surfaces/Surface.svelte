<script lang="ts">
  export let color: 'cyan'|'teal'|'green'|'red' = 'cyan'
  export let padding: 'tight'|'loose' = 'tight'
</script>

<style>
  div {
    --cyan: #56CCF2;
    --teal: #369696;
    --green: #B8F98C;
    --red: #EA9696;

    --tight: 8px;
    --loose: 12px;

    border: 3px solid black;
    padding: 50px;
    border-radius: 20px;
    box-shadow: 0px 4px black;
  }
</style>

<div style="background-color: var(--{color}); padding: var(--{padding})">
  <slot></slot>
</div>