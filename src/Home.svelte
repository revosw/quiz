<script lang="ts">
  import Participants from "./lib/components/Participants.svelte";
  import Password from "./lib/components/Password.svelte";
  import Column from "./lib/flex/Column.svelte";
  import Row from "./lib/flex/Row.svelte";
  import Spacer from "./lib/flex/Spacer.svelte";
  import Icon from "./lib/Icon.svelte";
  import Button from "./lib/surfaces/Button.svelte";
  let showPasswordBox = false;
  $: showPasswordBox;

  function togglePasswordBox() {
    showPasswordBox = !showPasswordBox;
  }

  function play() {}
</script>

<Column>
  <div />
  {#if true}
    <div style="visibility: {showPasswordBox ? 'visible' : 'hidden'}">
      <Password {togglePasswordBox} />
    </div>
  {/if}
  <Row align="center">
    <span>https://quiz.com</span>
    <Icon icon="📋" />
    <Spacer />
    <Button click={togglePasswordBox}>?</Button>
    <Button click={play}>Play</Button>
  </Row>
  <Participants />
</Column>
