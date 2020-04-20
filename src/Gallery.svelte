<script>
  export let images;
  import Image from './Image.svelte'
</script>

<style>
  section {
    display: flex;
    flex-wrap: wrap;
    margin: -0.5rem;
  }

  section>* {
    margin: 0.5rem;
  }

  section>h2 {
    flex-basis: 100%;
    padding-top: 2em;
    padding-bottom: 1em;
    text-align: center;
    font-size: 1.6em;
  }
</style>

<section>
  <h2>Gallery</h2>
  {#each images as image, index}
    <Image src={image} alt={index} />
  {:else}
    Loading...
  {/each}
</section>