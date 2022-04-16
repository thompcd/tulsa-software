<script>
import Ticker from '$lib/Ticker.svelte'

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

<div id="hero">
    <h1>local.</h1>
    <h1>reliable.</h1>
    <h1>software.</h1>
    <div id="ticker-container">
      <Ticker {...props}>
        <span class="ticker">Web UI/UX. Data. Automation. IOT. Manufacturing. Industrial. Small Business. Web UI/UX. Data. Automation. IOT. Manufacturing. Industrial. Small Business. Web UI/UX. Data. Automation. IOT. Manufacturing. Industrial. Small Business.</span>
      </Ticker>
    </div>
</div>

<style>
  @media(min-width: 768px){
    #hero{
    background-image: linear-gradient(rgba(78, 78, 78, 0), rgba(78, 78, 78, 0.5)),url("driller_lg.jpg");
        /* Position and center the image to scale nicely on all screens */
    background-repeat: no-repeat;
    background-size: cover;
    position: relative;
    text-align: right;
    background-color: white;
    display: flex;
    flex-direction: column;
    justify-content: center;
    min-width: 600px;
    border: 3px solid #162B49;
  }
  #hero h1{
    padding: 1rem 5rem;
    line-height: 7rem;
    font-size: 7em;
  }
  .ticker{
    color: white;
  }
}

@media(max-width: 767px){
  #hero{
    width: 100%;
  }
  #hero h1{
    line-height: 4rem;
    font-size: 4em;
  }
  .ticker{
    color: #162B49;
  }
}

  h1{
    color: #162B49;
    font-family:Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif
  }
  #ticker-container {
    padding: 0;
		width: 100%; 
		max-height: 28px; 
		overflow: hidden;
	}

  </style>