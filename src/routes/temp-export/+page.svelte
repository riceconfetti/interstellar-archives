<script>
	import rinn from '../../lib/rinn.json';
    import CharacterCard from '../../lib/CharacterCard.svelte';
</script>

<main>
	<div class="border">
		<div class="header">
			<div class="logo">
				<img alt="IA" src="/favicon.png" />
				<p>Interstellar Archives</p>
			</div>
			<p class="name">Rinn</p>
		</div>

        <div class= "cards">
            {#each Object.values(rinn) as char} 
                <CharacterCard currentCharacter={char.character} currentLightcone={char.lightcone}></CharacterCard>
            {/each}
        </div>
	</div>
</main>

<style lang="scss">
	:global(nav) {
		display: none !important;
	}

    main {
        padding: 2em;
        width: 100vw;
        box-sizing: border-box;
    }

    .border {
        border: 1px solid #ffffff33;
        height: 100%;
        width: 100%;
        padding: 2em;
        box-sizing: border-box;
    }

	.header {
		display: flex;
		width: 100%;
		box-sizing: border-box;
		padding: 0rem 1rem;
		justify-content: space-between;
		align-items: center;

        p {
			font-size: 13px;
			text-transform: uppercase;
			letter-spacing: 10px;
			color: #fff;
			text-shadow: #fff 1px 0 10px;
			background: none;
			text-decoration: none;
			
		}

        .logo {
            display: flex;
			gap: 20px;
			align-items: center;
			transition-duration: 0.4s;
            
            img {
				background: none;
				width: 4em;
			}
        }
	}

    .cards {
        margin-top: 2rem;
        width:100%;
        box-sizing: border-box;
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        gap: 2em;
    }
</style>
