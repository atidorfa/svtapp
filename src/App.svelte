<script>
    import Modal from './Modal.svelte';
    import AddPersonForm from './AddPersonForm.svelte';

	let people = [
		{ name: 'yoshi', beltColour: 'black', age: 25, id: 1 },
		{ name: 'mario', beltColour: 'orange', age: 45, id: 2 },
		{ name: 'luigi', beltColour: 'brown', age: 35, id: 3 }
	];

    const handleClick = (e, id) => {
        // console.log(e);
        people = people.filter((person) => person.id != id)
    }

    let number = 3;
    let showModal = false;

    const toggleModal = () => {
        showModal = !showModal;
    }

    const addPersonHandler = (e) => {
        // console.log(e.detail);
        const person = e.detail;
        people = [person, ...people];
        showModal = false;
    }

</script>

<!-- {#if number > 20}
    <p>Greater than 20</p>
{:else if number > 5}
    <p>Greater than 5</p>
{:else}
    <p>Not greater than 5</p>
{/if} -->

<Modal {showModal} on:click={toggleModal} >
    <div slot="title">
        <h3>Add a new person</h3>
    </div>
    <AddPersonForm on:addPerson={addPersonHandler} />
</Modal>
<!-- <Modal isPromo={true}/> -->

<main>
    <button on:click={toggleModal}>Add person</button>
	{#each people as person (person.id)}
        <div>
            <h4>{person.name}</h4>
            {#if person.beltColour === 'black'}
                <p><strong>MASTER NINJA</strong></p>
            {/if}
            <p>{person.age} years old, {person.beltColour} belt.</p>
            <button on:click="{(e) => handleClick(e, person.id)}">Delete</button>
        </div>
    {:else}
        <p>There are no people to show...</p>
    {/each}
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>