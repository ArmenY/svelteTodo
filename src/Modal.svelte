<script>
    import {createEventDispatcher} from "svelte";
    const dispatch = createEventDispatcher()

    export let title;
    export let description;


    const formSubmit = () => {
        const formValues = {
            totTitle: title,
            todoDescription: description,
            id:Math.random()
        }
        dispatch('addTodo', formValues)
    }
</script>

<form>
    <input type="text" placeholder="Todo Title" bind:value={title}>
    <input type="text" placeholder="Todo Description" bind:value={description}>
    <button on:click|preventDefault on:click={formSubmit}>Add Todo Item</button>
</form>

<style>

</style>