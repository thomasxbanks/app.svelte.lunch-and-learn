<script>
  import Card from './Card.svelte';

  let posts = [];
  import { onMount } from 'svelte'

  const getPosts = async () => {
    const endpoint = "http://scrummable.com/wp-json/wp/v2/posts?_embed"
    const raw = await fetch(endpoint)
    const response = await raw.json()
    console.log(response)
    return response;
  }

  onMount(async () => {
    posts = await getPosts()
  })
</script>

<style>

</style>

<section class="grid">
  <h2>Posts</h2>
  {#each posts as post, index}
    <Card {post} {index} />
  {/each}
</section>