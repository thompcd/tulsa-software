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
  import Ticker from '$lib/Ticker.svelte'

  export let posts
  let props = {
      direction: 'left',
      duration: 60,
      delay: 0,
      loop: true,
      pausing: true,
      alternate: false,
      animate: true,
      behavior: 'auto'
    };
</script>

<svelte:head>
  <title>Tulsa Software</title>
</svelte:head>

<section>
  <div id="hero">
    <h1>local.</h1>
    <h1>custom.</h1>
    <h1>software.</h1>
    <div id="ticker-container">
      <Ticker {...props}>
        Web UI/UX. Data. Automation. IOT. Manufacturing. Industrial. Small Business. Web UI/UX. Data. Automation. IOT. Manufacturing. Industrial. Small Business. Web UI/UX. Data. Automation. IOT. Manufacturing. Industrial. Small Business.
      </Ticker>
    </div>
  </div>
</section>
<section>
  <a href="/projects"><h1>/projects</h1></a>
  <ProjectsGrid {posts} />
</section>
  
<style>
  #hero{
    height: 600px;
    background-color: white;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
  #hero h1{
    padding: 1rem;
    line-height: 7rem;
    font-size: 7em;
    font-family:Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif
  }
  section{
    padding-bottom: 3rem;
  }
  h1{
    color: #162B49;
  }
  #ticker-container {

		width: 100%; 
		max-height: 28px; 
		overflow: hidden;
	}
  #ticker-container > *{
    color: slategray;
    opacity: 50%;
  }
</style>
