<script>
  export let name;
  import Header from './Header.svelte'
</script>

<style>

</style>

<svelte:head>
  <title>Svelte Lunch & Learn</title>
</svelte:head>

<main>
  <Header hero={true} {name} />
</main>