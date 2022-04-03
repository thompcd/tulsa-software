<script context="module">
  import {page} from '$app/stores'

</script>
<script>
    export let blogTitle = 'Tulsa Software'

    let path
    $: ({path} = $page)
	
	let w, h;
	let customUnderline = "";
	let underlineBox = "";
	let navStyle = "height 40px;";
	let liStyle = "padding-top: 0.45rem;";
	let iconStyle = "";	
</script>

<svelte:window  bind:innerHeight={h} bind:innerWidth={w}></svelte:window>

<header>
    <nav >
      <ul mobile-mode={ w < 480}>
        <li class="underline-box" data-selected={path === '/contact'}><a class='custom-underline' href="/contact">contact</a></li>
        <li class="underline-box" data-selected={path === '/blog'}><a class='custom-underline' href="/blog">posts</a></li>
        <li class="underline-box" data-selected={path === '/'}><a class='custom-underline' href="/">home</a></li>
      </ul>
    </nav>
</header>
<!-- 
<nav style={navStyle}>
	<ul>
		<li style={liStyle} id='home' class='{segment === undefined ? "selected" : ""} {underlineBox}' ><a class={customUnderline} rel=prefetch  href='index'>home</a></li>
		<li style={liStyle} class='{segment === "contact" ? "selected" : ""} {underlineBox}' ><a class={customUnderline} rel=prefetch  href='contact'>contact</a></li>
		<li style={liStyle} class='{segment === "blog" ? "selected" : ""} {underlineBox}' ><a class={customUnderline} rel=prefetch  href='blog'>blog</a></li>
	</ul>
</nav> -->

<!-- $: if (w < 480) {
    console.log("less than 480");
    customUnderline = "";
    underlineBox = "";
    navStyle = "height 40px;";
    liStyle = "padding-top: 0.8rem;";
    iconStyle = ""
}
$: if (w > 480){
    console.log("more than 480");
    customUnderline = "custom-underline";
    underlineBox = "underline-box";
    navStyle = "height: 58px;"
    liStyle = "";
    iconStyle = "height: 30px;";
} -->

<style>
	nav {
		border-bottom: 1px solid #2e68e6;
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
		/* height: 50px; */
	}

	#home{
		float: left;
		/* align-self: flex-start; */
	}

	#home img{
		height: 44px;
		padding: 6px 0 0px 0px;

	}

	#home a{
		padding: 0 0 ;
	}

	a {
		text-decoration: none;
		padding: 0 0.5em .1em 0.5em;
		display: block;
		color: #f3f3f3;
	}

	/* a:hover {
		color: #2e9be6;
	} */
</style>