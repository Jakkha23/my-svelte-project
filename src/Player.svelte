<script>
    import { createEventDispatcher } from 'svelte'

    const dispatch = createEventDispatcher()

	export let name;
	export let points;
	let showControls = false

	const addPoint = () => (points += 1)
	const removePoint = () => (points -= 1)
	const toggleControls = () => (showControls = !showControls)
    const onDelete = () => dispatch("removeplayer", name)
</script>

<style>
	h1{
		color: rgb(11, 109, 109);
		margin: 5px;
	}
	h3{
		margin-bottom: 10px;
		margin-left: 10px;
	}
	.card {
		border: 1px solid black;
		border-radius: 10px;
		background-color: 	#8787e0;
		margin: 5px;
	}
	.btnExpand{
		background-color: aquamarine;

	}
	.btnRed{
		background-color: rgb(250, 9, 9);

	}
	.btnAdd{
		background-color: rgb(110, 169, 228);

	}
	.btnSubtract{
		background-color: rgb(230, 148, 148);

	}
	button{
		font-size: medium;
		border: 1px solid gray;
		border-radius: 10px;
	}
</style>

	<div class="card">
		<h1>{name}
		<button class="btnExpand" on:click={toggleControls}>
		{#if showControls}close{:else}edit{/if}
		</button>
        <button class="btnRed" on:click={onDelete}>Delete Player</button>
        </h1>
		<h3>{points}</h3>
		{#if showControls}
		<button class="btnAdd" on:click={addPoint}>+1</button>
		<button class="btnSubtract" on:click={removePoint}>-1</button>
		<input type="number" bind:value={points} />
		{/if}
	</div>
