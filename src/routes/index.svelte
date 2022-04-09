<script>
import Ticker from '$lib/Ticker.svelte'
import DiGithubBadge from 'svelte-icons/di/DiGithubBadge.svelte'
import FaSlack from 'svelte-icons/fa/FaSlack.svelte'

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

<div id="ticker-container">
  <Ticker {...props}>
    <h2>Web UI/UX. Data. Automation. IOT. Manufacturing. Industrial. Small Business. Web UI/UX. Data. Automation. IOT. Manufacturing. Industrial. Small Business. Web UI/UX. Data. Automation. IOT. Manufacturing. Industrial. Small Business.</h2>
  </Ticker>
</div>

<h1>Hi, I'm Corey.</h1>
<h1>I do contract software work. <i>For Tulsa</i></h1>

<div class="icons">
  <a href="https://github.com/tulsasoftware">
    <DiGithubBadge />
  </a>
  <a href="/">
    <FaSlack />
  </a>
</div>

<a href="/projects"><h2>/projects</h2></a>
Samples of work the group has participated in.

<a href="/contact"><h2>/contact</h2></a>
Samples of work the group has participated in.

<style>
  #ticker-container {
    margin: -16px 0 32px 0;
		width: 100%; 
		max-height: 28px; 
		overflow: hidden;
	}

  .icons{
    display: flex;
  }
  .icons * {
    width: 64px;
    height: 64px;
  }
</style>
