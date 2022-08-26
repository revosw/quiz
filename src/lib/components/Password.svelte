<script lang="ts">
  import Icon from "../Icon.svelte";

  import Input from "../surfaces/Input.svelte";
  import RoundButton from "../surfaces/RoundButton.svelte";
  import Surface from "../surfaces/Surface.svelte";

  export let togglePasswordBox: () => any;

  function submitPassword() {}
</script>

<div>
  <Input placeholder="Password" />
  <RoundButton click={submitPassword}>
    <Icon icon="check" />
  </RoundButton>
  <RoundButton click={togglePasswordBox} color="red">
    <Icon icon="cross" />
  </RoundButton>
</div>

<style>
  div {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: var(--tight)
  }
</style>