<script context="module">
  import {page} from '$app/stores'

</script>
<script>
	import DrawnSvg  from '$lib/DrawnSvg.svelte'
    export let blogTitle = 'Tulsa Software'

    let path
    $: ({path} = $page)
	
	export let w, h;
</script>

<header>
    <nav >
      <ul mobile-mode={ w < 480}>
        <li class="underline-box" id="home"><a href="/">
			<DrawnSvg h="120" w="120" condition={true} duration=2500 fill="white" color="black"></DrawnSvg></a>
		</li>
        <li class="underline-box" data-selected={path.startsWith('/contact')}><a class='custom-underline' href="/contact">contact</a></li>
        <li class="underline-box" data-selected={path.startsWith('/projects')}><a class='custom-underline' href="/projects">projects</a></li>
        <li class="underline-box" data-selected={path.startsWith('/blog')}><a class='custom-underline' href="/blog">posts</a></li>
        <li class="underline-box" data-selected={path ==='/'}><a class='custom-underline' href="/">home</a></li>
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

	.underline-box a {line-height: 3.5rem;}

	.custom-underline {
		position: relative;
		display: inline-block;
		font-size: 16px;
		font-weight: 400;
		text-align: center;
	}

	.custom-underline::after{
		content: '';
		display: block;
		clear: both;
		position:absolute;
		transition: 0.5s ease all;
		background-color: white;
		height: 2px !important;
		top: 75%;
	}

	.custom-underline,
	.custom-underline:hover,
	.custom-underline:focus,
	.custom-underline:active {
		color: #fff;
		text-decoration: none;
	}

	[data-selected = "true"] .custom-underline::after{
		width: 80%;
		left: 10%;
		background-color: rgb(198, 32, 46);
	}

	[data-selected = "false"] .custom-underline::after {
		width: 20%;
		left: 40%;
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