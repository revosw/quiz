<script lang="ts">
  import Button from "../surfaces/Button.svelte";
import Input from "../surfaces/Input.svelte";
import Surface from "../surfaces/Surface.svelte";

  export let togglePasswordBox: () => any;

  function submitPassword() {}
</script>

<Surface padding="tight">
  <Input placeholder="Password" />
  <Button click={submitPassword}>✅</Button>
  <Button click={togglePasswordBox} color="red">❌</Button>
</Surface>
