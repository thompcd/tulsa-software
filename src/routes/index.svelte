<script>
import Ticker from '$lib/Ticker.svelte'
import Props from '$lib/Props.svelte'

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

<div>
  <Ticker {...props}>
    <h2>Web UI/UX. Data. Automation. IOT. Manufacturing. Industrial. Small Business. Web UI/UX. Data. Automation. IOT. Manufacturing. Industrial. Small Business. Web UI/UX. Data. Automation. IOT. Manufacturing. Industrial. Small Business.</h2>
  </Ticker>
</div>

<h1>Hi, I'm Corey.</h1>
<h1>I do contract software work. <i>For Tulsa</i></h1>

//social icons

<a href="/projects"><h2>/projects</h2></a>
Samples of work the group has participated in.

<a href="/contact"><h2>/contact</h2></a>
Samples of work the group has participated in.

<style>
  	div {
      margin: -16px 0 32px 0;
		width: 100%; 
		max-height: 28px; 
		overflow: hidden;
	}
</style>
