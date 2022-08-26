<script lang="ts">
  import Column from "../flex/Column.svelte";

  import Row from "../flex/Row.svelte";
  import Icon from "../Icon.svelte";
  import Surface from "../surfaces/Surface.svelte";

  const people = [
    {
      name: "Guy",
      admin: true,
    },
    {
      name: "Adam",
    },
    {
      name: "Shrek",
    },
  ];
</script>

<Surface>
  <Column>
    {#each people as person}
      <Row align='center'>
        <span style="flex-grow: 1">
          {person.name}
        </span>
        {#if person.admin}
          <Icon icon="🛡️" />
        {/if}
      </Row>
    {/each}
  </Column>
</Surface>

<style>
</style>
