<script>
  import Nav from '$lib/Nav.svelte'
  import Footer from '$lib/Footer.svelte'

  let width;
  let height;

</script>
<svelte:window  bind:innerHeight={height} bind:innerWidth={width}></svelte:window>

<Nav blogTitle={'Tulsa Software'} w={width} h={height} />

<main style="padding: 1em">
  <slot />
</main>

<Footer />

<style>
  main{
    margin: 0 5rem;
  }
</style>