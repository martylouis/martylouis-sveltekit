<script context="module">
  import { STORYBLOK_ENV } from '$lib/env_vars';
  import { useStoryblokApi } from '@storyblok/svelte';

  export const load = async () => {
    const storyblokApi = useStoryblokApi();
    const {
      data: { story }
    } = await storyblokApi.get('cdn/stories/home', {
      version: STORYBLOK_ENV
    });
    return {
      props: { story }
    };
  };
</script>

<script lang="ts">
  import { StoryblokComponent, useStoryblokBridge } from '@storyblok/svelte';
  import { onMount } from 'svelte';

  export let story: any;

  onMount(() => {
    useStoryblokBridge(story.id, (newStory) => (story = newStory));
  });
</script>

<div>
  {#if story}
    <StoryblokComponent blok={story.content} />
  {/if}
</div>
