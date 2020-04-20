<script>
  export let name;
  import Header from './Header.svelte'
  import Image from './Image.svelte'
</script>

<style>
  main {
    max-width: calc(2rem + 67ch);
    margin-right: auto;
    margin-left: auto;
    padding: 1rem;
  }

  main>*+* {
    margin-top: 1.5em;
  }
</style>

<svelte:head>
  <title>Svelte Lunch & Learn</title>
</svelte:head>

<Header hero={true} {name} />
<Image src="http://placekitten.com/1920/768" alt="A lovely kitten" />
<main>
  <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Molestias officiis, ipsam voluptatem porro reprehenderit quasi cum maxime natus! Ipsum rerum modi ullam, magnam a placeat aperiam excepturi iure iusto repellendus?</p>
</main>