<script context="module">
  import {page} from '$app/stores'

</script>
<script>
	import DrawnSvg  from '$lib/DrawnSvg.svelte'
    export let blogTitle = 'Tulsa Software'

	let starPath = "233.828,0 301.053,117.393 436.328,116.914 368.275,233.828 436.328,350.742 301.053,350.264 233.828,467.656 166.605,350.264 31.328,350.742 99.381,233.828 31.328,116.914 166.605,117.393 ";
    let path
    $: ({path} = $page)
	
	export let w, h;
</script>

<header>
    <nav >
      <ul mobile-mode={ w < 480}>
        <li class="underline-box" id="home"><a href="/">
			<DrawnSvg h="200" w="200" condition={true} path={starPath} duration=2500 fill="white" color="black"></DrawnSvg></a>
		</li>
        <li class="underline-box" data-selected={path === '/contact'}><a class='custom-underline' href="/contact">contact</a></li>
        <li class="underline-box" data-selected={path === '/blog'}><a class='custom-underline' href="/blog">posts</a></li>
        <li class="underline-box" data-selected={path === '/'}><a class='custom-underline' href="/">home</a></li>
      </ul>
    </nav>
</header>

<style>
	header{
		padding-bottom: 72px;
	}
	nav {
        background-color: #162B49;
		border-bottom: 4px solid #EBAD21;
		font-weight: 300;
		padding: .5rem 1.5rem;
	}

	ul {
		margin: 0;
		padding: 0;
	}

	/* clearfix */
	ul::after {
		content: '';
		display: block;
		clear: both;
	}

    ul > li {
        height: 58px;
        padding-top: 0.45rem;
    }

    ul[mobile-mode='true']{
        height: 40px;
    }

	li {
		display: block;
		float: right;
		transition: ease-in;
	}

	#home{
        display: block;
		float: left;
		margin-top: -28px;
	}

	#home a{
        color: white;
        font-size: x-large;
        text-transform: uppercase;
        font-family: "Roboto Condensed";
	}

	a {
		text-decoration: none;
		padding: 0 0.5em .1em 0.5em;
		display: block;
	}
</style>