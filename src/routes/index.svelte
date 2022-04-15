<script context="module">
  export async function load({fetch}) {
    try {
      const res = await fetch('/projects/all.json')
      const data = await res.json()
      return {
        props: data
      }
    } catch (err) {
      console.log('500:', err)
    }
  }
</script>

<script>
  import ProjectsGrid from '$lib/ProjectsGrid.svelte'
  import Hero from '$lib/Hero.svelte'

  export let posts;
</script>

<svelte:head>
  <title>Tulsa Software</title>
</svelte:head>

<section>
  <Hero />
</section>

<section>
  <a href="/projects"><h1>/projects</h1></a>
  <ProjectsGrid maxWidth="1fr" {posts} />
</section>
  
<style>
  section{
    padding-bottom: 3rem;
  }
  h1{
    color: #162B49;
  }
</style>
