<script>
	import * as Romanice from 'romanice';

	const { romanice } = Romanice;
	const standardConverter = romanice();

	export let currentCharacter = {
		name: 'Unknown',
		element: '',
		path: '',
		image: '',
		rarity: 4,
		lvl: 1,
		max_lvl: 20,
		eidolons: 0,
		stats: [
			{ type: 'hp', value: 0 },
			{ type: 'atk', value: 0 },
			{ type: 'def', value: 0 },
			{ type: 'spd', value: 0 },
			{ type: 'crit rate', value: 0 },
			{ type: 'crit dmg', value: 0 }
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
		<div id="gradient" />
		<svg
			width="329"
			height="530"
			viewBox="0 0 329 530"
			fill="none"
			xmlns="http://www.w3.org/2000/svg"
		>
			<path
				d="M 7.4217 0.464 V 8.4447 H 0.3528 V 529.375 H 315.373 V 528.67 H 1.0575 V 9.1494 H 8.1265 V 1.1687 L 380.667 1.1687 V -1 H 7.4217 Z"
				fill="white"
				fill-opacity="0.39"
			/>
			<path
				d="M0.705151 0.816357L0.705181 5.08021H4.95525V0.816357H0.705151Z"
				fill="white"
				fill-opacity="0.39"
			/>
		</svg>

		<img src={currentCharacter.image} alt={currentCharacter.name} />
		<div class="eidolons {currentCharacter.element}">
			{#each Array(currentCharacter.eidolons) as _, index (index)}
				<div class="eid active"><p>{index + 1}</p></div>
			{/each}
			{#each Array(6 - currentCharacter.eidolons) as _, index (index)}
				<div class="eid"><p>{index + 1 + currentCharacter.eidolons}</p></div>
			{/each}
		</div>
	</div>
	<div class="character-stats">
		<div class="character-heading">
			<div class="character-name">
				<h3>{currentCharacter.name}</h3>
				<img
					src="./hsr_data/elements/{currentCharacter.element}.png"
					alt={currentCharacter.element}
				/>
			</div>
			<div class="character-path">
				<img src="./hsr_data/paths/{currentCharacter.path}.png" alt={currentCharacter.path} />
				<h4>{currentCharacter.path}</h4>
			</div>
			<div class="character-ascension">
				{#each Array(currentCharacter.max_lvl / 10 - 2) as phase, index (index)}
					<div class="ascension active">
						<img src="./ascension-active.svg" alt="active {index + 1}" />
					</div>
				{/each}
				{#each Array(8 - (currentCharacter.max_lvl / 10 - 2)) as phase, index (index)}
					<div class="ascension inactive">
						<img src="./ascension-inactive.svg" alt="inactive {index + 1}" />
					</div>
				{/each}
			</div>
			<div class="character-lvl">
				<p class="lvl-current">
					Lv. {currentCharacter.lvl}/<span class="lvl-max">{currentCharacter.max_lvl}</span>
				</p>
			</div>
		</div>

		<h4 class="stats-label">Stats</h4>

		<div class="basic-stats">
			{#each currentCharacter.stats as stat, index (index)}
				<div class="character-stat">
					<p class="stat-label">{stat.type}</p>
					<p class="stat-value">{stat.value}</p>
				</div>
			{/each}
		</div>

		<div class="lightcone">
			<img src="./hsr_data/lightcones/pastandfuture_crop.png" alt="Past and Future Lightcone Art" />
			<div class="super">
				<div class="super-bg">
					<p>{standardConverter.toRoman(currentLightcone.super)}</p>
				</div>
			</div>
			<div class="lightcone-info">
				<div class="info-lvl">
					<p class="lvl-label">Lv.</p>
					<p class="lightcone-lvl">
						<span class="current-lvl">{currentLightcone.lvl}</span>/{currentLightcone.max_lvl}
					</p>
				</div>
				<div class="lightcone-stats">
					<div class="stat">
						<img src="./hsr_data/stats/hp.svg" alt="hp" />
						<p>{currentLightcone.hp}</p>
					</div>
					<div class="stat">
						<img src="./hsr_data/stats/atk.svg" alt="atk" />
						<p>{currentLightcone.atk}</p>
					</div>
					<div class="stat">
						<img src="./hsr_data/stats/def.svg" alt="def" />
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
		font-family: 'Exo 2';
		display: flex;
		height: 550px;
		width: 700px;

		background: radial-gradient(
					951.35% 121.24% at 61.13% 147.34%,
					rgba(217, 217, 217, 0.1) 0%,
					rgba(217, 217, 217, 0) 100%
				)
				/* warning: gradient uses a rotation that is not supported by CSS and may not behave as expected */,
			radial-gradient(
					172.22% 73.7% at 92.49% 0%,
					rgba(217, 217, 217, 0.1) 0%,
					rgba(217, 217, 217, 0) 100%
				)
				/* warning: gradient uses a rotation that is not supported by CSS and may not behave as expected */,
			radial-gradient(
					312.92% 115.65% at 0% 0%,
					rgba(217, 217, 217, 0.1) 0%,
					rgba(217, 217, 217, 0) 100%
				)
				/* warning: gradient uses a rotation that is not supported by CSS and may not behave as expected */;
		filter: drop-shadow(0px 5.63788px 5.63788px rgba(0, 0, 0, 0.25));
		backdrop-filter: blur(1.09934px);

		.character-image {
			display: flex;
			box-sizing: border-box;
			position: relative;
			overflow: clip;
			width: 320px;
			justify-content: center;

			#gradient {
				position: absolute;
				width: 50%;
				height: 100%;
				left: 0px;
				top: 0px;

				background: linear-gradient(90deg, rgba(0, 0, 0, 0.4) 0%, rgba(0, 0, 0, 0) 100%);
			}

			svg {
				position: absolute;
				padding: 0.6rem;
				top: 0;
				left: 0;
			}

			img {
				height: 105%;
				margin-top: 1rem;
			}
			.eidolons {
				position: absolute;
				bottom: 1rem;
				display: flex;
				gap: 1rem;
				width: 100%;
				flex-direction: column;

				.eid {
					display: flex;
					box-sizing: border-box;
					flex-direction: row;
					justify-content: flex-end;
					align-items: center;
					padding: 0 0.5rem 0.25rem;
					width: 45px;
					height: 1.1rem;
					border-radius: 0px 50px 50px 0px;
					background: linear-gradient(
						270deg,
						#000000 44.6%,
						rgba(0, 0, 0, 0.00503391) 107.8%,
						rgba(40, 40, 40, 0) 107.81%
					);

					&.active {
						width: 60px;
					}

					p {
						line-height: 100%;
						font-size: 1.8rem;
						font-weight: 600;
						color: white;
					}
				}

				&.wind .eid.active {
					background: linear-gradient(
						270deg,
						#3cab77 44.6%,
						rgba(20, 37, 21, 0.00503391) 107.8%,
						rgba(164, 227, 180, 0) 107.81%
					);
				}
			}
		}

		.character-stats {
			display: flex;
			flex-direction: column;
			justify-content: space-between;
			align-items: flex-start;
			padding: 1.8rem;
			gap: 1rem;
			width: 380px;
			background: rgba(19, 19, 19, 0.74);
			border-radius: 38.0557px 0px 0px 0px;

			.character-heading {
				width: 100%;
				display: flex;
				flex-direction: column;
				gap: 0.6em;
				.character-name {
					display: flex;
					justify-content: space-between;
					font-size: 1.6rem;
					width: 100%;

					img {
						width: 2rem;
						height: 2rem;
					}
				}

				.character-path {
					display: flex;
					gap: 0.2rem;
					align-items: center;
					text-transform: capitalize;
					font-size: 1rem;
					padding: 0.3rem 0.3rem 0.4rem 0.3rem;
					background-color: rgba(255, 255, 255, 0.05);

					h4 {
						line-height: 0.8rem;
						padding-bottom: 0.1rem;
					}

					img {
						width: 1rem;
					}
				}

				.character-ascension {
					display: flex;
					align-items: center;
					gap: 0.1rem;

					.ascension {
						box-sizing: border-box;
						width: 1.2rem;

						img {
							width: 100%;
							height: 100%;
						}

						&.inactive {
							padding: 0.1rem;
						}
					}
				}

				.character-lvl {
					font-weight: 600;
					font-size: 1.2rem;
					.lvl-max {
						color: #606060;
						font-size: 0.9rem;
					}
				}
			}

			.stats-label {
				width: 100%;
				height: 1.6rem;
				font-size: 1rem;
				font-weight: 600;
				text-align: center;
				background-color: white;
				color: black;
				padding: 0.2rem;
				border-radius: 1rem;
			}

			.basic-stats {
				display: flex;
				flex-direction: column;
				width: 100%;
				gap: 0.4rem;

				.character-stat {
					display: flex;
					width: 100%;
					justify-content: space-between;
					align-items: center;
					text-transform: uppercase;
				}
			}

			.lightcone {
				display: flex;
				position: relative;
				width: 100%;
				height: 100%;
				overflow: hidden;
				flex-direction: column;
				border: 1.41px solid #ffffff;
				box-shadow: 0px 0px 5.631886005401611px 0px #ffffff40;
				justify-content: space-between;

				.super {
					display: flex;
					padding: 0.4rem;
					z-index: 1;
					justify-content: flex-end;

					.super-bg {
						border-radius: 2rem;
						background: #000000bd;
						width: 1.5rem;
						height: 1.5rem;
						display: flex;
						align-items: center;
						justify-content: center;

						p {
							font-size: 1rem;
							text-align: center;
							font-family: 'Castoro';
							color: #c9993b;
						}
					}
				}

				.lightcone-info {
					display: flex;
					flex-direction: row;
					box-sizing: border-box;
					z-index: 1;
					padding: 0.2rem 0.4rem;
					width: 100%;
					background: black;
					justify-content: space-between;
					font-size: 0.8rem;

					.info-lvl {
						display: flex;
						gap: 1rem;
						.lightcone-lvl .current-lvl {
							color: #e59801;
						}
					}

					.lightcone-stats {
						display: flex;
						gap: 0.6rem;

						.stat {
							box-sizing: border-box;
							display: flex;
							align-items: center;
							gap: 0.3rem;

							img {
								position: relative;
								top: 0.1rem;
								width: 1rem;
								height: 1rem;
							}

							p {
								font-size: 0.8rem;
								line-height: 0.8rem;
							}
						}
					}
				}

				img {
					position: absolute;
					top: -1em;
					width: 100%;
				}
			}
		}
	}
</style>
