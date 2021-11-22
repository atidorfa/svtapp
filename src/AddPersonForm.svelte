<script>
    let name;
    let beltColour;
    let age;

    const handleSubmit = () => {
        console.log(name, beltColour, age)
    }
</script>

<form on:submit|preventDefault={handleSubmit}>
    <input type="text" placeholder="Name" bind:value={name}>
    <input type="text" placeholder="Belt colour" bind:value={beltColour}>
    <input type="number" bind:value={age}>
    <button>Add person</button>
</form>

<style>

</style>