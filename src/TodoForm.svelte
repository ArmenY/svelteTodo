<script>
    import {createEventDispatcher} from "svelte";
    const dispatch = createEventDispatcher()
    export let todoTitle;
    export let todoDescription;
    const formSubmit = () => {
        const formValues = {
            todoTitle,
            todoDescription,
            id: Math.random()
        }
        dispatch('addTodo', formValues)
    }
</script>

<form class="todoForm" on:submit|preventDefault={formSubmit}>
    <input class="todoForm__titleInput" type="text" placeholder="Todo Title" bind:value={todoTitle}>
    <input class="todoForm__descriptionInput" type="text" placeholder="Todo Description"
           bind:value={todoDescription}>
    <button class="todoForm__submitBtn">Add Todo Item</button>
</form>

<style>
    .todoForm {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        width: 100%;
        height: fit-content;
        max-width: 350px;
        margin: 0 auto;
        background: #fff;
        border-radius: 4px;
        padding: 50px 30px;
    }

    .todoForm__titleInput,
    .todoForm__descriptionInput {
        margin-bottom: 20px;
        padding: 5px 10px;
        border-radius: 4px;
        background: #e4b45c;
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
        padding: 10px 30px;
        cursor: pointer;
    }
</style>