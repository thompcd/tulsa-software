<script context="module">
  import {page} from '$app/stores'

</script>
<script>
	import IoIosMenu from 'svelte-icons/io/IoIosMenu.svelte'
	import TulsaFlag  from '$lib/TulsaFlag.svelte'
    export let blogTitle = 'Tulsa Software'

	let mobilemode = false;
	let showMenu = false;
    let path
    $: ({path} = $page)
	
	$: mobilemode = w < 480
	export let w, h;
</script>

<header>
    <nav mobile-nav={mobilemode}>
		<div id="hamburger" on:click={() => showMenu = !showMenu}>
			<IoIosMenu />
		</div>
      	<ul class="links" show-menu={showMenu} mobile-mode={ mobilemode }>
			<li id="home">
				<a href="/">
					<TulsaFlag h="120" w="120" condition={!mobilemode}></TulsaFlag>
				</a>
			</li>
			<li class="underline-box" data-selected={path.startsWith('/contact')}><a class='custom-underline' href="/contact">contact</a></li>
			<li class="underline-box" data-selected={path.startsWith('/projects')}><a class='custom-underline' href="/projects">projects</a></li>
			<li class="underline-box" data-selected={path.startsWith('/blog')}><a class='custom-underline' href="/blog">posts</a></li>
			<li class="underline-box" data-selected={path ==='/'}><a class='custom-underline' href="/">home</a></li>
      	</ul>
    </nav>
</header>

<style>
	/* common styles */
	nav {
        background-color: #162B49;
		border-bottom: 4px solid #EBAD21;
		font-weight: 300;
		padding: .5rem 1.5rem;
	}
	#hamburger{
		height: 28px;
		width: 28px;
		padding: 8px;
		color: white;
		display: block;
		position: absolute;
		right: 0;
		top: 0;
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
	li {
		list-style: none;
		display: block;
		float: right;
		transition: ease-in;
	}
	a {
		text-decoration: none;
		padding: 0 0.5em .1em 0.5em;
		display: block;
	}

	/* mobile nav */
	/* keep #home as a spacer, but disable it as an option */
	[mobile-mode = 'true'] #home{
		height: 14px;
	}
	/* inactive mobile menu */
	[mobile-nav = 'true']{
		height: 40px;
		position: relative;
		background-color: #162B49;
		padding: 0;
	}
	/* style dropdown menu */
	[mobile-nav = 'true'] .links li{
		color: white;
		padding: 14px 0;
		text-decoration: none;
		font-size: 17px;
		display: block;
		background-color: #162B49;
		width: 100%;
		text-align: center;
	}
	/* add stripe to bottom of menu */
	[mobile-nav = 'true'] .links li:last-child{
		border-bottom: 4px solid #EBAD21;
	}
	[mobile-nav = 'true'] .links li:hover{
		background-color: #ddd;
  		color: black;
	}
	/* hamburger placement */
	[mobile-nav='true'] > #hamburger{
		float: right;
	}
	[mobile-nav='false'] > #hamburger{
		display: none;
	}
	[mobile-nav='true'] [show-menu='false']{
		display: none;
	}
	[mobile-nav='true'] [show-menu='true']{
		display: block;
	}
    ul[mobile-mode='true']{
        height: 40px;
    }


	/* full size nav */
	header > * > [mobile-mode='false']{
		padding-bottom: 72px;
	}
	[mobile-nav='false']{
		height: 58px;
		margin-bottom: 58px;
	}
	[mobile-mode='false'] .underline-box a {line-height: 3.5rem;}

	[mobile-mode='false'] .custom-underline {
		position: relative;
		display: inline-block;
		font-size: 16px;
		font-weight: 400;
		text-align: center;
	}

	[mobile-mode='false'] .custom-underline::after{
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

	[mobile-mode='false'] [data-selected = "true"] .custom-underline::after{
		width: 80%;
		left: 10%;
		background-color: rgb(198, 32, 46);
	}

	[mobile-mode='false'] [data-selected = "false"] .custom-underline::after {
		width: 20%;
		left: 40%;
	}

	[mobile-mode='false'] #home{
        display: block;
		float: left;
		margin-top: -28px;
	}

	[mobile-mode='false'] #home a{
        color: white;
        font-size: x-large;
        text-transform: uppercase;
        font-family: "Roboto Condensed";
	}
</style>