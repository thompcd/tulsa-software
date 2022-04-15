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

<footer>
  <div class="icons">
    <a href="https://github.com/tulsasoftware">
      <DiGithubBadge />
    </a>
    <a href="/">
      <FaSlack />
    </a>
  </div>

  <div id="ticker-container">
    <Ticker {...props}>
      <h2>Web UI/UX. Data. Automation. IOT. Manufacturing. Industrial. Small Business. Web UI/UX. Data. Automation. IOT. Manufacturing. Industrial. Small Business. Web UI/UX. Data. Automation. IOT. Manufacturing. Industrial. Small Business.</h2>
    </Ticker>
  </div>
</footer>

<style>
  footer {
    text-align: center;
    margin-top: 2rem;
    margin-bottom: 1rem;
  }
  #ticker-container {
    margin: -16px 0 32px 0;
    margin-top: 1rem;

		width: 100%; 
		max-height: 28px; 
		overflow: hidden;
	}

  .icons{
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 1em;
  }
  .icons * {
    width: 64px;
    height: 64px;
  }
</style>
