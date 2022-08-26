<script lang="ts">
  import Admin from "./Admin.svelte";
  import Home from "./Home.svelte";
import Row from "./lib/flex/Row.svelte";
  import Question from "./Question.svelte";
  import Results from "./Results.svelte";

  let page = '/'
</script>

<main>
  <Row>
    <button on:click={() => page = '/'}>/</button>
    <button on:click={() => page = '/question'}>question</button>
    <button on:click={() => page = '/results'}>results</button>
    <button on:click={() => page = '/admin'}>admin</button>
  </Row>
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
