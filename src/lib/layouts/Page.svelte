<script lang="ts">
  import { StoryblokComponent, storyblokEditable } from '@storyblok/svelte';
  export let blok: any;
</script>

<div use:storyblokEditable={blok}>
  {#each blok.body as blok}
    <StoryblokComponent {blok} />
  {/each}
</div>
