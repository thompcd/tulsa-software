<script>
    import ProjectCard from '$lib/ProjectCard.svelte'
  
    export let posts = []
    export let maxWidth = "1fr";
  </script>
  
  <section style="grid-template-columns: repeat(auto-fit, minmax(250px, {maxWidth}))">
    {#each posts as post (post.slug.current)}
      <ProjectCard {post} />
    {/each}
  </section>
  
  <style>
    section {
      display: grid;
      gap: 3rem 2rem;
      margin-top: 3rem;
    }
  </style>
  