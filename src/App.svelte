<script>
	export let name;
	let seatingPlan = "";
	let rows = 5;
	let columns = 5;
	const handleClick = (name) => {
		students = students.filter((student) => student.name != name);
	}
	let students = [
		{name: 'TAN YOU REN', priority: []},	
		{name: 'JOHN DOE', priority: []},
		{name: 'TAN YOU REN', priority: []},	
		{name: 'JOHN DOE', priority: []},{name: 'TAN YOU REN', priority: []},	
		{name: 'JOHN DOE', priority: []},{name: 'TAN YOU REN', priority: []},	
		{name: 'JOHN DOE', priority: []},{name: 'TAN YOU REN', priority: []},	
		{name: 'JOHN DOE', priority: []},{name: 'TAN YOU REN', priority: []},	
		{name: 'JOHN DOE', priority: []},{name: 'TAN YOU REN', priority: []},	
		{name: 'JOHN DOE', priority: []},{name: 'TAN YOU REN', priority: []},	
		{name: 'JOHN DOE', priority: []},
	]
</script>


<main>
	<h1>Seating Plan for {name}</h1>
	<button on:click={handleClick}>Generate Random Seating Plan</button>
	<input type="number" bind:value={rows} min="1">
	<input type="number" bind:value={columns} min="1">
	<p>Rows: {rows} Columns: {columns}</p>
	<table>
		{#each Array(rows) as _, rowIndex}
			<tr>
				{#each Array(columns) as _, columnIndex}
					<td>{rowIndex * columns + columnIndex + 1}</td>
				{/each}
			</tr>
		{/each}
	</table>
	{#each students as student}
		<div style=" background-color:#F8F8F8; padding: 5px; border-radius:10%;">
			<h4 class="unselectable">{student.name}</h4>
			<p  class="unselectable">{student.seat}</p>
			<button on:click={() => {handleClick(student.name)}}>Delete</button>
		</div>
	{:else}
		<p>No students</p>
	{/each}
	
	
</main>

<style>
	td {
		padding: 10px;
		margin: 10px;
		background-color: #ff3e00;
	}
	.unselectable{
		-moz-user-select: -moz-none;
		-khtml-user-select: none;
		-webkit-user-select: none;

		/*
			Introduced in IE 10.
			See http://ie.microsoft.com/testdrive/HTML5/msUserSelect/
		*/
		-ms-user-select: none;
		user-select: none;
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