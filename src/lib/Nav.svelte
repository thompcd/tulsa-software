<script context="module">
  import {page} from '$app/stores'

</script>
<script>
    export let blogTitle = 'Tulsa Software'

    let path
    $: ({path} = $page)
	
	export let w, h;
</script>

<header>
    <nav >
      <ul mobile-mode={ w < 480}>
        <li class="underline-box" id="home"><a href="/">⭐</a></li>
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