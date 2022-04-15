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
  
    export let posts
    export let authors
  </script>
  
  <svelte:head>
    <title>Projects</title>
  </svelte:head>
  
  <h1>Recent posts</h1>
  
  <PostsGrid {posts} />