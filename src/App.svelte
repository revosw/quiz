<script lang="ts">
  import Admin from "./Admin.svelte";
  import Home from "./Home.svelte";
  import Question from "./Question.svelte";
  import Results from "./Results.svelte";

  const page = '/'
</script>

<main>
  {#if page === "/"}
    <Home />
  {:else if page === "/question"}
    <Question />
  {:else if page === "/results"}
    <Results />
  {:else if page === "/admin"}
    <Admin />
  {/if}
</main>
