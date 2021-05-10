<script>
	let name = "jakob";
	let CircleX = 1
	let CircleY = 1
	let count = 0

	function increase() {
		count = count +1
	}
	function reset() {
		count = 0
	}
</script>

<main>
	<h1>Hello {name}!</h1>
	<button class="btn1" on:click={increase}>Click me</button>
	<button class="btn2" on:click={increase}>click me too</button>
	<button class="btn3" on:click={reset}>'SUBTLE OFF-WHITE COLORING'</button>
	<p>{count}</p>
</main>

<style>
	main {
		background-color: #f8f8ff;
	}

	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #fc7b03;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	.btn1 {
		background-color: #fc7b03;
	}
	.btn2 {
		background-color: aquamarine;
	}
	.btn3 {
		background-color: 	#f8f8ff;
		border-radius: 12px;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>