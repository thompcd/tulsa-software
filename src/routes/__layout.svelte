<script>
  import Nav from '$lib/Nav.svelte'
  import Footer from '$lib/Footer.svelte'
</script>

<Nav blogTitle={'Tulsa Software'} />

<main style="padding: 1em">
  <slot />
</main>

<Footer />