<script>
  export let images;
  import Image from './Image.svelte'
</script>

<style>

</style>

<section class="grid">
  <h2>Gallery</h2>
  {#each images as image, index}
    <Image src={image} alt={index} />
  {:else}
    Loading...
  {/each}
</section>