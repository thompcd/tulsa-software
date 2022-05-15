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
    <h1 class="striped">reliable.</h1>
    <h1 class="striped">tulsan.</h1>
    <h1 class="striped">software.</h1>
</div>

<style>
  @media(min-width: 768px){
    #hero{
    background-repeat: no-repeat;
    background-size: cover;
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: center;
    min-width: 600px;
  }
  #hero h1{
    padding: 1rem 5rem;
    line-height: 7rem;
    font-size: 7em;
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
}

  h1{
    color: #162B49;
    font-family:Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif
  }

  .striped{
    background-image: linear-gradient(transparent 60%, rgba(198, 32, 46,.5) 40%);
    width:fit-content;
  }

  </style>