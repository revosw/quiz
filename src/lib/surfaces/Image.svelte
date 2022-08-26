<script lang="ts">
  import Surface from "./Surface.svelte";
  export let src: string;
</script>

<Surface padding="none">
  <img {src} style="height: 100%; width: 100%" alt="Illustrates what the question is about" />
</Surface>
