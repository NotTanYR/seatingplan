<script>
	export let name;
	let seatingPlan = "";
	let rows = 5;
	let columns = 6;
	const handleClick = (name) => {
		students = students.filter((student) => student.name != name);
	}
	let students = [
		{name: 'TAN YOU REN', priority: []}
	]
</script>


<main>
	<h1>Seating Plan for {name}</h1>
	<button on:click={handleClick}>Generate Random Seating Plan</button>
	<input type="number" bind:value={rows} min="1">
	<input type="number" bind:value={columns} min="1">
	<p>Rows: {rows} Columns: {columns}</p>
	<div class="grid-container" style="display: grid; grid-template-rows: repeat({rows}, 1fr); grid-template-columns: repeat({columns}, 1fr);">
		{#each Array(rows * columns) as _, rowIndex}
			<div class="grid-item">{rowIndex + 1}</div>  
		{/each}
	</div>
</main>

<style>
	.grid-container {
		display:grid;
		background-color: #2196F3;
		margin: 0 auto;
		background-color: #2196F3; 
		padding: 10px; 	
	}
	.grid-item {
		border: 3px solid rgba(0, 0, 0, 0.8);
		font-size: 30px;
		text-align: center;
		background-color: blue;
		color: white;
	}
	main {
		text-align: center;
		position: relative;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>