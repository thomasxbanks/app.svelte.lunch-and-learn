<script>
  import Button from "./Button.svelte";
  import ButtonContainer from "./ButtonContainer.svelte";
  import Card from "./Card.svelte";
  let loading = false;
  let page = 1;
  let posts = [];
  import { onMount } from "svelte";

  const getPosts = async (page = 1) => {
    loading = true;
    const endpoint = `http://scrummable.com/wp-json/wp/v2/posts?_embed&per_page=3&page=${page}`;
    const raw = await fetch(endpoint);
    const response = await raw.json();
    console.log(response);
    posts = [...posts, ...response];
    loading = false;
  };

  onMount(async () => {
    await getPosts();
  });
</script>

<style>
  .grid {
    max-width: 1200px;
    margin-right: auto;
    margin-left: auto;
  }
  section {
    width: max-content;
    margin-right: auto;
    margin-left: auto;
    padding-top: 2rem;
    padding-bottom: 2rem;
  }
</style>

<section class="grid">
  <h2>Posts</h2>
  {#each posts as post, index}
    <Card {post} {index} />
  {/each}
</section>
<section>
  <ButtonContainer>
    <Button size="large" on:click={() => getPosts(++page)}>
      {loading ? 'Loading...' : 'Load more'}
    </Button>
  </ButtonContainer>
</section>
