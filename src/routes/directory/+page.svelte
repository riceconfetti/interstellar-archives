<script>
	import IndexCard from '../../lib/IndexCard.svelte';
	import SpaceHeading from '../../lib/SpaceHeading.svelte';
   const Bronya = {
      name: "Bronya",
      image: "/hsr_data/headshots/Bronya.png",
      rarity: 5
   }

	const March_7th = {
      name: "March 7th",
      image: "/hsr_data/headshots/March 7th.png",
      rarity: 4
   }
</script>

<div class="container">
	<div id="header">
		<div id="filter" />
		<SpaceHeading title="Directory" subtitle="Add characters to your directory here"/>
	</div>

	<div id="directory">
		<IndexCard character={Bronya}/>
		<IndexCard character={March_7th}/>
	</div>
</div>

<style lang="scss">
	.container {
      position: absolute;
		display: flex;
      box-sizing: border-box;
      width: 100%;
      padding: 4em;
		margin-top: 6em;	
      gap: 3em;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		text-transform: uppercase;
		color: #fff;
		#header {
			display: flex;
         box-sizing: border-box;
			width: 100%;
			justify-content: space-between;
			align-items: baseline;

         SpaceHeading {
            text-align: right;
            box-sizing: border-box;
         }
		}
		#directory {
			display: flex;
			gap: 1rem;
		}
	}
</style>
