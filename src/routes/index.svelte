<script context="module">
  export async function load({fetch}) {
    try {
      const res = await fetch('/blog/all.json')
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
  import PostsGrid from '$lib/PostsGrid.svelte'
  import ProjectsGrid from '$lib/ProjectsGrid.svelte'

  export let posts
</script>

<svelte:head>
  <title>Tulsa Software</title>
</svelte:head>

<section>
  <a href="/projects"><h1>/projects</h1></a>
  <ProjectsGrid {posts} />
</section>

<section>
  <a href="/posts"><h1>/posts</h1></a>
  <PostsGrid {posts} />
</section>

<section>
  <a href="/contact"><h1>/contact</h1></a>
</section>
  
<style>
  section{
    padding-bottom: 3rem;
  }
  h1{
    color: #162B49;
  }
</style>
