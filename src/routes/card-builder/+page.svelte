<script>
	import SpaceHeading from '../../lib/SpaceHeading.svelte';
	import CharacterCard from '../../lib/CharacterCard.svelte';

	let currentCharacter = {
		name: 'Bronya',
		element: 'wind',
		path: 'Harmony',
		image: '/hsr_data/headshots/Bronya.png',
		rarity: 5,
		lvl: 60,
		max_lvl: 60,
		stats: [
			{ type: 'hp', value: 2009 },
			{ type: 'atk', value: 1312 },
			{ type: 'def', value: 744 },
			{ type: 'spd', value: 104 },
			{ type: 'critrate', value: 14.3 },
			{ type: 'critdmg', value: 116.5 }
		]
	};

	let currentLightcone = {
		name: '',
		super: 2,
		lvl: 50,
		max_lvl: 50,
		hp: 550,
		atk: 244,
		def: 229,
		img: ''
	};
</script>

<div id="container">
	<div class="builder">
		<SpaceHeading title="Card Builder" subtitle="Showcase your character stats" />
		<CharacterCard {currentCharacter} {currentLightcone}/>
	</div>
</div>

<style lang="scss">
	#container {
		position: absolute;
		justify-content: right;
		display: flex;
		box-sizing: border-box;
		margin-top: 6em;
		padding: 4em;
		width: 100%;
	}
</style>
