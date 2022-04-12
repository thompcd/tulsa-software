<script>
	import { draw } from 'svelte/transition';
	import { quintOut } from 'svelte/easing';
	
    export let fill = "none";
    export let color = "black";
    export let strokewidth = "0.1px"
    export let duration = 1500;
    export let condition = false;
	export let w, h;

</script>
<div class="logo-container" style="height:{h};width:{w}">
	<svg viewBox="{h/2} {w/2} {h} {w}" style="height:{h};width:{w}" xmlns="http://www.w3.org/2000/svg">
		{#if condition}
		<g fill="#ebad21">
			<circle cx="{w}" cy="{h}" r="{w/2}"/>
			<path d="m{w + 45} {h + 65}v55l15 15 15-15v-55zm-120 0v55l15 15 15-15v-55zm60 30v55l15 15 15-15v-55zm60-28.5v53.5l15 15 15-15v-53.5zm-245-81.5v30h600v-30z"/>
		</g>
		<circle cx="{w}" cy="{h}" r="75" fill="#c6202e"/>
		<path d="m{w} {h - 22} 21.8-15.8-3 26.7 24.6 10.8-24.6 10.9 3 26.7-21.8-15.9-21.7 15.9 2.9-26.7-24.7-10.9 24.7-10.8-2.9-26.7z" fill="#f8f1e0"/>
		{/if}
	</svg>
</div>
<style>
	svg {
		display: block;
	}
</style>