<script>
	let name = 'atidorfa';
	let linkname = 'Google'

	const handleClick = () => {
		linkname = 'Google';
	};

	const handleInput = (e) => {
		linkname = e.target.value;
	};
</script>

<main>
	<h1>Hello {name}!</h1>
	<p style="color: {linkname};">This is a link to <a href="https://google.com.ar">{linkname}</a></p>
	<button on:click={handleClick}>Update</button>
	<!-- <input type="text" on:input={handleInput} value={linkname}> -->
	<input type="text" bind:value={linkname}>
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