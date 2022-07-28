<script lang="ts">
  import { storyblokEditable, StoryblokComponent } from '@storyblok/svelte';
  export let blok: any;
</script>

<div use:storyblokEditable={blok}>
  {#each blok.columns as blok}
    <StoryblokComponent {blok} />
  {/each}
</div>
