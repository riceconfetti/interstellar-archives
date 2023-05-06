<script>
	import Nav from '../lib/Nav.svelte';
</script>

<Nav />

<div id="overlay">
	<slot />
</div>

<style lang="scss">
	:global(body) {
		font-family: Audiowide, Open Sans, Sans Serif;
		background: url('/stars.jpg');
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
		z-index: -99; /* Specify a stack order in case you're using a different order for other elements */
	}
</style>
