<script>
  export let src;
  export let alt;
  export let caption = false;
  export let hero = false;
</script>

<style>
  figure {
    width: 100%;
    height: auto;
  }

  figure:not(.hero) {
    width: calc(33.33% - 1rem);
    padding: 0.5rem;
  }

  figure.hero img {
    object-fit: cover;
  }

  figcaption {
    font-size: 0.8em;
    color: dimgray;
  }
</style>

<figure class:hero>
  <img src={src} alt={alt}>
  {#if caption}
    <figcaption>{caption}</figcaption>
  {/if}
</figure>