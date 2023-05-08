<script>
	export let character = {
		name: '',
		image: '',
		rarity: 4
	};
</script>

<div class="card">
	<div class="background">
		<img alt={character.name} src={character.image} />
	</div>
	<div class="info" class:five-star={character.rarity == 5} class:four-star={character.rarity == 4}>
		<h3>{character.name}</h3>
		<div class="rarity">
			{#each Array(character.rarity) as _, index (index)}
				<svg
					width="22"
					height="22"
					viewBox="0 0 22 22"
					fill="none"
					xmlns="http://www.w3.org/2000/svg"
				>
					<path
						d="M11.1374 0.425903C11.1374 0.425903 11.4409 6.06257 13.7509 8.37263C16.061 10.6827 21.6977 10.9862 21.6977 10.9862C21.6977 10.9862 16.061 11.2896 13.7509 13.5997C11.4409 15.9097 11.1374 21.5464 11.1374 21.5464C11.1374 21.5464 10.8339 15.9097 8.52387 13.5997C6.21381 11.2896 0.577148 10.9862 0.577148 10.9862C0.577148 10.9862 6.21381 10.6827 8.52387 8.37263C10.8339 6.06257 11.1374 0.425903 11.1374 0.425903Z"
						fill="#FFD070"
					/>
				</svg>
			{/each}
			
		</div>
		<div class="bar" class:five-star={character.rarity == 5} class:four-star={character.rarity == 4} />
	</div>
</div>

<style lang="scss">
	.card {
		width: 200px;
		height: 345px;
		position: relative;
		border: .2rem solid #ffffff00;
		transition-duration: .5s;

		&:hover {
			background:rgba(255, 255, 255, 0.37);
			transform: scale(1.01);
			transition:ease .5s;
			border: .2rem solid #fff;
		}
	}
	.background {
		width: 200px;
		height: 345px;
		background: url('../indexGradient.png');
		overflow: hidden;
		display: flex;
		align-items: center;
		justify-content: center;
		img {
			height: 100%;
		}
	}

	.info {
		position: absolute;
		width: 100%;
		bottom: 0;
		text-align: center;
		font-family: 'Exo 2';
		font-size: 1.2rem;
		font-weight: 600;
		text-transform: capitalize;
		display: flex;
		flex-direction: column;
		gap: 0.7rem;
		height: max-content;

		&.five-star {
			background: linear-gradient(180deg, rgba(255, 184, 38, 0) 0%, rgba(249, 169, 6, 0.295) 100%);
			
		}

		&.four-star {
			background: linear-gradient(180deg, rgba(225, 38, 255, 0) 0%, rgba(127, 6, 249, 0.295) 100%);

		}

		.rarity {
			display: flex;
			align-items: center;
			justify-content: center;
			padding: 0;

			svg {
				margin: 0 -0.2rem;
			}

			
		}

		.bar {
				height: 0.5rem;
				width: 100%;

				&.five-star {
					background-color: #FFD070;
				}

				&.four-star {
					background-color: #AF86FF;
				}
			}

		
	}
</style>
