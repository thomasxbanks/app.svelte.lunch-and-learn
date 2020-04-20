<script>
  export let name;
  export let hero;
</script>

<style>
  header {
    padding: 2rem;
    background-color: whitesmoke;
    border-bottom: 0.125rem solid tomato;
  }

  h1 {
    color: tomato;
  }

  .hero {
    font-size: 2em;
    font-weight: bold;
    text-align: center;
  }
</style>

<header>
  <h1 class:hero>Hello {name}!</h1>
</header>