<script>
    import {createEventDispatcher} from "svelte";

    const dispatch = createEventDispatcher()
    let isVisible = true

    export let title;
    export let description;


    const formSubmit = () => {
        const formValues = {
            totTitle: title,
            todoDescription: description,
            id: Math.random()
        }
        dispatch('addTodo', formValues)
    }
</script>

<div class="todoForm--backDrop" class:todoForm__active={isVisible}>
    <form class="todoForm">
        <input class="todoForm__titleInput" type="text" placeholder="Todo Title" bind:value={title}>
        <input class="todoForm__descriptionInput" type="text" placeholder="Todo Description" bind:value={description}>
        <button class="todoForm__submitBtn" on:click|preventDefault on:click={formSubmit}>Add Todo Item</button>
    </form>
</div>

<style>
    .todoForm {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        width: 100%;
        height: 100%;
        max-width: 350px;
        margin: 0 auto;
    }

    .todoForm__titleInput,
    .todoForm__descriptionInput {
        margin-bottom: 20px;
        padding: 5px 10px;
        border-radius: 4px;
        background: #e4b45ccc;
        outline: none;
        border: none;
        font-family: sans-serif;
    }

    .todoForm__titleInput::placeholder,
    .todoForm__descriptionInput::placeholder {
        color: #fff;
    }

    .todoForm__submitBtn {
        background: #e4b45c;
        font-family: sans-serif;
        font-weight: 700;
        color: #fff;
    }

    .todoForm--backDrop {
        position: fixed;
        width: 100%;
        height: 100%;
        background: #000000cc;
    }
</style>