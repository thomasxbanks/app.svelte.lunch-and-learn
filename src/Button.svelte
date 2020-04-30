<script>
  export let size = "regular";
  export let variant = "default";

  const classes = `${size} ${variant}`;
</script>

<style>
  button {
    display: inline-block;
    padding: 0.5em 1.5em;
    border-width: 0.125em;
    border-style: solid;
    border-radius: 0.25em;
    line-height: 1em;
  }
  .default {
    background-color: tomato;
    color: white;
  }
  .ghost {
    border-color: tomato;
    color: tomato;
  }
  .small {
    font-size: 0.75rem;
  }
  .regular {
    font-size: 1rem;
  }
  .large {
    font-size: 1.25rem;
  }
</style>

<button class={classes} on:click>
  <slot />
</button>
