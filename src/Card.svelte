<script>
  export let index;
  export let post;
  import Image from './Image.svelte';
  import { fly } from 'svelte/transition'
  const transition = {
    x: 0,
    y: 80,
    duration: 300,
    delay: (index + 1) * 100
  }
</script>

<style>
  article {
    max-width: 380px;
    padding: 0.5rem;
    background-color: white;
    border: 0.0625rem solid silver;
    border-radius: 0.25rem;
    box-shadow: 0.125rem 0.125rem 0.125rem rgba(0, 0, 0, 0.15);
    margin: 0.5rem;
  }

  h3 {
    font-weight: bold;
    font-size: 1.25em;
    margin-top: 2em;
    margin-bottom: 1em;
  }
</style>

<article in:fly={transition} id="Post-{index}">
  <Image hero={true} src={post._embedded["wp:featuredmedia"][0].source_url} alt="Cat" />
  <h3>{@html post.title.rendered}</h3>
  {@html post.excerpt.rendered}
</article>