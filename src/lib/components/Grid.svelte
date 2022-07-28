<script lang="ts">
  import { storyblokEditable, StoryblokComponent } from '@storyblok/svelte';
  export let blok: any;
</script>

<div use:storyblokEditable={blok} class="feature-grid count-{blok.count}">
  {#each blok.columns as blok}
    <StoryblokComponent {blok} />
  {/each}
</div>

<style lang="postcss">
  .feature-grid {
    @apply grid gap-2;
  }

  .count-2 {
    @apply grid-cols-2;
  }

  .count-3 {
    @apply grid-cols-3;
  }

  .count-4 {
    @apply grid-cols-4;
  }
</style>
