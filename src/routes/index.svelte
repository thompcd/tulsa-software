<script>
import Ticker from '$lib/Ticker.svelte'

let tickerProps = {
      direction: ['left', [ 'left', 'right', 'top', 'bottom' ]],
      duration: 30,
      delay: 0,
      loop: true,
      pausing: true,
      alternate: false,
      behavior: ['auto', [ 'auto', 'always' ]]
    };
</script>
<svelte:head>
  <title>Tulsa Software</title>
</svelte:head>

<Ticker {...tickerProps}>
  Web UI/UX. Data. Automation. IOT. Manufacturing. Industrial. Small Business. <i>In Tulsa</i> Wooooooooooooooooo
</Ticker>
<h2>I'm Corey. I do contract software work. Sometimes solo. Sometimes not.</h2>

//social icons

<a href="/projects"><h2>/projects</h2></a>
Samples of work the group has participated in.

<a href="/contact"><h2>/contact</h2></a>
Samples of work the group has participated in.

