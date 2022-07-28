<script lang="ts">
  import { storyblokEditable } from '@storyblok/svelte';
  export let blok: any;
</script>

<div use:storyblokEditable={blok}>
  <div>{blok.headline}</div>
</div>
