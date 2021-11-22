<script>
	let firstName = 'ati';
	let lastName = 'dorfa'
	let pColour = 'Enter a color'

	$: fullName = `${firstName}${lastName}`;
	// $: console.log(pColour);
	$: {
		console.log(pColour);
		console.log(fullName);
	}
	const handleClick = () => {
		pColour = 'Orange';
	};

	const handleInput = (e) => {
		pColour = e.target.value;
	};
</script>

<main>
	<h1 style="color: {pColour};">Hello {fullName}!</h1>
	<p>This is a link to <a href="https://google.com.ar">Google</a></p>
	<button on:click={handleClick}>Update</button>
	<!-- <input type="text" on:input={handleInput} value={pColour}> -->
	<input type="text" bind:value={pColour}>
	<br>
	<input type="text" bind:value={firstName}>
	<input type="text" bind:value={lastName}>

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