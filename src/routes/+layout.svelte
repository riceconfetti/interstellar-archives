<script>
	import Nav from '../lib/Nav.svelte';
	import { fade } from 'svelte/transition';

	export let data;

	$: ({ pathname } = data);
</script>

<Nav />
<div id="blue-overlay" />
<div id="overlay" />
<div id="stars" />

{#key pathname}
	<main in:fade={{ duration: 300, delay: 400 }} out:fade={{ duration: 300 }}>
		<slot />
	</main>
{/key}

<style lang="scss">
	:global(*) {
		margin: 0;
	}
	:global(body) {
		font-family: Audiowide, Open Sans, Sans Serif;
	}
	:global(#stars) {
		background: url('/stars.jpg');
		position: fixed; /* Sit on top of the page content */
		width: 100%; /* Full width (cover the whole page) */
		height: 100%; /* Full height (cover the whole page) */
		top: 0;
		left: 0;
		right: 0;
		bottom: 0;
		z-index: -99;
	}
	:global(#overlay) {
		position: fixed; /* Sit on top of the page content */
		width: 100%; /* Full width (cover the whole page) */
		height: 100%; /* Full height (cover the whole page) */
		top: 0;
		left: 0;
		right: 0;
		bottom: 0;
		background-color: rgba(0, 0, 0, 0.1);
		z-index: -9; /* Specify a stack order in case you're using a different order for other elements */
	}

	:global(#blue-overlay) {
		position: fixed; /* Sit on top of the page content */
		width: 100%; /* Full width (cover the whole page) */
		height: 100%; /* Full height (cover the whole page) */
		top: 0;
		left: 0;
		right: 0;
		bottom: 0;
		background: rgba(19, 84, 182, 0.6);
		mix-blend-mode: hue;
		z-index: -98;
	}
</style>
