<script>
	import { draw } from 'svelte/transition';
	import { quintOut } from 'svelte/easing';
	
    export let path = "M2 1 h1 v1 h1 v1 h-1 v1 h-1 v-1 h-1 v-1 h1 z";
    export let fill = "none";
    export let color = "black";
    export let strokewidth = "0.1px"
    export let duration = 1500;
    export let condition = false;
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
<svg viewBox="8.06 -4.855 120 90" xmlns="http://www.w3.org/2000/svg">
	{#if condition}
		<g transform="matrix(0.160374, 0, 0, 0.160374, 26.303761, 0)" transition:draw="{{duration: 1500, easing: quintOut}}">
			<polygon
				transition:draw="{{duration: 4500, easing: quintOut}}"
				fill="white"
				stroke="white"
				stroke-width="0.1px"
				points="233.828,0 301.053,117.393 436.328,116.914 368.275,233.828 436.328,350.742 301.053,350.264 233.828,467.656 166.605,350.264 31.328,350.742 99.381,233.828 31.328,116.914 166.605,117.393 "
			/>
		</g>
	{/if}
</svg>
<style>
	svg {
		display: block;
		margin-top: -28px;
		height: 200px;
		width: 200px;
	}
</style>