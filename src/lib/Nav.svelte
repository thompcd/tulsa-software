<script context="module">
  import {page} from '$app/stores'

</script>
<script>
	import DrawnSvg  from '$lib/DrawnSvg.svelte'
    export let blogTitle = 'Tulsa Software'

	let starPath = "M 33.003 369.492 c 2.233 3.869 6.36 6.25 10.825 6.25 c 0.015 0 0.029 0 0.044 0 l 128.002 -0.453 l 63.606 111.078 c 2.228 3.889 6.366 6.289 10.848 6.289 c 4.481 0 8.62 -2.399 10.848 -6.288 l 63.608 -111.079 l 128 0.453 c 0.015 0 0.029 0 0.044 0 c 4.465 0 8.592 -2.382 10.825 -6.25 c 2.241 -3.881 2.231 -8.665 -0.022 -12.538 l -64.392 -110.626 l 64.392 -110.626 c 2.255 -3.873 2.265 -8.657 0.022 -12.538 c -2.233 -3.869 -6.36 -6.25 -10.825 -6.25 c -0.015 0 -0.029 0 -0.044 0 l -128 0.453 L 257.176 6.288 C 254.948 2.399 250.81 0 246.328 0 c -4.482 0 -8.62 2.399 -10.848 6.289 l -63.606 111.079 l -128.002 -0.453 c -0.015 0 -0.029 0 -0.044 0 c -4.465 0 -8.592 2.382 -10.825 6.25 c -2.241 3.881 -2.232 8.665 0.022 12.538 l 64.392 110.625 L 33.025 356.954 C 30.77 360.827 30.762 365.611 33.003 369.492 Z M 122.683 252.616 c 2.263 -3.888 2.263 -8.689 0 -12.576 l -57.071 -98.049 l 113.449 0.402 c 0.015 0 0.029 0 0.044 0 c 4.48 0 8.62 -2.398 10.848 -6.289 l 56.375 -98.449 l 56.377 98.45 c 2.229 3.89 6.367 6.288 10.848 6.288 c 0.016 0 0.029 0 0.044 0 l 113.447 -0.402 l -57.071 98.049 c -2.263 3.887 -2.263 8.688 0 12.576 l 57.071 98.049 l -113.447 -0.401 c -0.015 0 -0.028 0 -0.044 0 c -4.479 0 -8.619 2.398 -10.848 6.289 l -56.377 98.449 l -56.375 -98.449 c -2.228 -3.892 -6.367 -6.289 -10.848 -6.289 c -0.015 0 -0.029 0 -0.044 0 l -113.449 0.4 L 122.683 252.616 Z";
	let condition = false;
    let path
    $: ({path} = $page)
	
	export let w, h;
</script>

<header>
    <nav >
      <ul mobile-mode={ w < 480}>
        <li class="underline-box" id="home"><a href="/">
			<DrawnSvg condition={condition} path={starPath} duration=2500></DrawnSvg></a>
		</li>
		<button on:click={() => condition = !condition}>
			show svg
		</button>
        <li class="underline-box" data-selected={path === '/contact'}><a class='custom-underline' href="/contact">contact</a></li>
        <li class="underline-box" data-selected={path === '/blog'}><a class='custom-underline' href="/blog">posts</a></li>
        <li class="underline-box" data-selected={path === '/'}><a class='custom-underline' href="/">home</a></li>
      </ul>
    </nav>
</header>

<style>
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