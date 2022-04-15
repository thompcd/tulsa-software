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
  
    export let posts
  </script>
  
  <svelte:head>
    <title>Projects</title>
  </svelte:head>
  
  <h1>All Projects</h1>
  
  <ProjectsGrid {posts} />