<script>
	export let name;
	let species = 'hooman';
	$: titling = `${name} ${species}`;
	
	const handleClick = () => {
		species = 'doggo'; 
	};

	const handleInput = (eventparameter) => {
		species = eventparameter.target.value;
	}
</script>

<main>
	<h1>Hello {name}!</h1>
	<p>I am {species}</p>
	<button on:click={handleClick}>Change to doggo</button>
	<label for="species-io">Change into:</label>
	<input bind:value={species} type="text" name="species-io" id="species-io" on:input={handleInput}>
	<br>
	<h2>You meet {titling}</h2>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
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