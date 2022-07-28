<script context="module">
  import '../app.css';
  import { apiPlugin, storyblokInit } from '@storyblok/svelte';
  import Feature from '$lib/components/Feature.svelte';
  import Grid from '$lib/components/Grid.svelte';
  import Page from '$lib/layouts/Page.svelte';
  import Teaser from '$lib/components/Teaser.svelte';

  import { STORYBLOK_ACCESS_TOKEN } from '$lib/env_vars';

  storyblokInit({
    accessToken: STORYBLOK_ACCESS_TOKEN,
    use: [apiPlugin],
    components: {
      feature: Feature,
      grid: Grid,
      page: Page,
      teaser: Teaser
    }
  });
</script>

<main class="prose">
  <slot />
</main>
