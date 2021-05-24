<script>
	import Navbar from './Navbar.svelte'
	import Player from './Player.svelte'
	import AddPlayer from './AddPlayer.svelte'

	let players = [
	]

	const addPlayer = (e) => {
		const newPlayer = e.detail;
		players = [...players, newPlayer];
	}

	const removePlayer = e => {
		players = players.filter(player => player.name !== e.detail)
	}
</script>

<style>
	:global(body){
		background-image: url('bluewave.jpg'); 
	}
	.addMenu {
		text-align: center;
	}
	.p1 {
		color: aliceblue;
		text-align: center
	}
</style>


	<Navbar />
<div class="container">
	<div class="addMenu">
		<AddPlayer on:addplayer={addPlayer} />
	</div>

	{#if players.length === 0}
	<p class="p1">No Players</p>
	{:else}
		{#each players as player}
			<Player name={player.name} points={player.points} on:removeplayer={removePlayer} />
	{/each}
	{/if}
</div>

