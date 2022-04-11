<script>
	import { draw } from 'svelte/transition';
	import { quintOut } from 'svelte/easing';
	
    export let path = "M2 1 h1 v1 h1 v1 h-1 v1 h-1 v-1 h-1 v-1 h1 z";
    export let fill = "none";
    export let color = "black";
    export let strokewidth = "0.1px"
    export let duration = 1500;
    export let condition = false;
	export let w, h;

</script>

<!-- <svg viewBox="0 0 5 5" xmlns="http://www.w3.org/2000/svg">
	<path transition:draw="{{duration: 20000, easing: quintOut}}"
				d={path}
				fill={fill}
				stroke={color}
				stroke-width={strokewidth}}
				>
				</path>

</svg> -->
<svg viewBox="8.06 -4.855 120 90" style="height:{h};width:{w}" xmlns="http://www.w3.org/2000/svg">
	{#if condition}
		<g transform="matrix(0.160374, 0, 0, 0.160374, 26.303761, 0)" transition:draw="{{duration: duration, easing: quintOut}}">
			<polygon
				transition:draw="{{duration: duration, easing: quintOut}}"
				fill={fill}
				stroke={color}
				stroke-width={strokewidth}
				points={path}
			/>
		</g>
	{/if}
</svg>
<style>
	svg {
		display: block;
	}
</style>