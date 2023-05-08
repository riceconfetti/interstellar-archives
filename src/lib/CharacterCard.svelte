<script>
	export let currentCharacter = {
		name: 'Unknown',
		element: '',
		path: '',
		image: '',
		rarity: 4,
		lvl: 1,
		max_lvl: 20,
		stats: [
			{ type: 'hp', value: 0 },
			{ type: 'atk', value: 0 },
			{ type: 'def', value: 0 },
			{ type: 'spd', value: 0 },
			{ type: 'critrate', value: 0 },
			{ type: 'critdmg', value: 0 }
		]
	};

	export let currentLightcone = {
		name: '',
		super: 1,
		lvl: 1,
		max_lvl: 20,
		hp: 0,
		atk: 0,
		def: 0,
		img: ''
	};
</script>

<div id="card">
	<div class="character-image">
		<img src={currentCharacter.image} alt={currentCharacter.name} />
		<div class="eidolons {currentCharacter.element}">
			{#each Array(6) as _, index (index)}
				<div class="eid"><p>{index + 1}</p></div>
			{/each}
		</div>
	</div>
	<div class="character-stats">
		<div class="character-heading">
			<h3>{currentCharacter.name}</h3>
			<img src="./element/{currentCharacter.element}.png" alt={currentCharacter.element} />
			<div class="path">
				<img src="./path/{currentCharacter.path}.png" alt={currentCharacter.path} />
				<h4>{currentCharacter.path}</h4>
			</div>
			<div class="character-ascension">
				{#each Array(currentCharacter.max_lvl / 10 - 2) as phase, index (index)}
					<img src="./ascension-active.svg" alt="active {index + 1}" />
				{/each}
				{#each Array(8 - (currentCharacter.max_lvl / 10 - 2)) as phase, index (index)}
					<img src="./ascension-inactive.svg" alt="inactive {index + 1}" />
				{/each}
			</div>
			<div class="character-lvl">
				<p class="lvl-label">Lv.</p>
				<p class="lvl-current">{currentCharacter.lvl}/</p>
				<p class="lvl-max">{currentCharacter.max_lvl}</p>
			</div>
		</div>

		<h4 class="stats-label">Stats</h4>

		{#each currentCharacter.stats as stat, index (index)}
			<div class="character-stat">
				<p class="stat-label">{stat.type}</p>
				<p class="stat-value">{stat.value}</p>
			</div>
		{/each}

		<div class="lightcone">
			<div class="super">{currentLightcone.super}</div>
			<div class="lightcone-info">
				<div class="lightcone-lvl">
					<p>Lv.</p>
					<p class="currentLvl">{currentLightcone.lvl}</p>
					<p class="maxLvl">{currentLightcone.max_lvl}</p>
				</div>
				<div class="lightcone-stats">
					<div class="stat">
						<img src="./stats/hp.svg" alt="hp" />
						<p>{currentLightcone.hp}</p>
					</div>
					<div class="stat">
						<img src="./stats/atk.svg" alt="atk" />
						<p>{currentLightcone.atk}</p>
					</div>
					<div class="stat">
						<img src="./stats/def.svg" alt="def" />
						<p>{currentLightcone.def}</p>
					</div>
				</div>
			</div>
		</div>
	</div>
</div>

<style lang="scss">
	#card {
		color: white;
        font-family: "Exo 2";
		.character-image {
			position: relative;
			.eidolons {
				position: absolute;
				bottom: 1rem;
				display: flex;
				flex-direction: column;
				.eid p {
					color: white;
				}
			}
		}
	}
</style>
