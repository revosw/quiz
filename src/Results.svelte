<script lang="ts">
  import Column from "./lib/flex/Column.svelte";
  import Row from "./lib/flex/Row.svelte";
  import Icon from "./lib/Icon.svelte";
  import RoundButton from "./lib/surfaces/RoundButton.svelte";

  import Surface from "./lib/surfaces/Surface.svelte";

  const numQuestions = 8;
  const people = [
    {
      name: "Larry",
      correct: [true, true, false, true, true, false, false, false],
    },
    {
      name: "Mary",
      correct: [true, false, true, true, false, true, false, false],
    },
    {
      name: "Carrie",
      correct: [true, true, true, true, false, false, false, false],
    },
    {
      name: "Gary",
      correct: [true, false, true, true, false, false, false, false],
    },
  ].sort((a, b) => a.correct.length - b.correct.length);

  function isLeading(person: typeof people[number]) {
    const highestScore = people[0].correct.filter(c => c).length;
    return person.correct.filter(c => c).length === highestScore;
  }
</script>

<Surface padding="none">
  <div
    class="result-grid"
    style="grid-template-columns: repeat({numQuestions + 2}, max-content)"
  >
    {#each people as person, rowIndex}
      {#if isLeading(person)}
        <Icon icon="crown" />
      {:else}
        <div />
      {/if}
      <span style="place-self: center right">{person.name}</span>
      {#each person.correct as correct, columnIndex}
        {#if correct}
          <RoundButton click={() => {}}>
            <Icon icon="check" />
          </RoundButton>
        {:else}
          <div />
        {/if}
      {/each}
    {/each}
  </div>
</Surface>

<style>
  .result-grid {
    place-items: center;
    padding: var(--loose);
    display: grid;
    gap: var(--loose);
    grid-template-columns: min-content max-content;
  }
</style>
