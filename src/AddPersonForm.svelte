<script>
    import { createEventDispatcher } from 'svelte';

    let dispatch = createEventDispatcher();
    
    let name;
    let beltColour;
    let age;
    let skills = [];

    const handleSubmit = () => {
        // Person object
        const person = {
            name: name,
            beltColour: beltColour,
            age: age,
            skills: skills,
            id: Math.random()
        };

        dispatch('addPerson', person);
    };
</script>

<form on:submit|preventDefault={handleSubmit}>
    <input type="text" placeholder="Name" bind:value={name}>
    <input type="number" placeholder="Age" bind:value={age}>
    <p>Skills:</p>
    <!-- <input type="checkbox" bind:checked={fighting}> Fighting<br>
    <input type="checkbox" bind:checked={shuriken}> Shuriken<br>
    <input type="checkbox" bind:checked={running}> Running<br> -->
    <input type="checkbox" bind:group={skills} value="fighting"> Fighting<br>
    <input type="checkbox" bind:group={skills} value="shuriken"> Shuriken<br>
    <input type="checkbox" bind:group={skills} value="running"> Running<br>
    <p>Belt colour:</p>
    <select bind:value={beltColour}>
        <option value="black">black</option>
        <option value="orange">orange</option>
        <option value="brown">brown</option>
        <option value="white">white</option>
    </select>
    <button>Add person</button>
</form>

<style>

</style>