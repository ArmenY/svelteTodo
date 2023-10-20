<script>
    import Modal from "./Modal.svelte";
    import Card from "./Card.svelte";
    import TodoForm from "./TodoForm.svelte";

    let showModal = false
    const toggleModal = () => {
        showModal = !showModal
    }

    export let todoItems = [];
    const addTodo = (e) => {
        let todoItem = e.detail
        todoItems = [todoItem, ...todoItems]
        showModal = false
    }
</script>

<Modal {showModal} on:click={toggleModal}>
    <TodoForm on:addTodo={addTodo} on:click={toggleModal}/>
</Modal>
<main>
    <div class="todo__wrapper">
        <h1 class="todo__heading">Your Todo List</h1>
        <button on:click={toggleModal}>Create New ToDo</button>
    </div>
    <Card bind:todoItems/>
</main>
<style>
    body {
        padding: 0;
        margin: 0;
    }

    .todo__wrapper {
        display: flex;
        align-items: center;
        justify-content: space-between;
        background: #e4b45c;
        padding: 20px;
    }

    .todo__heading {
        text-align: center;
        font-family: sans-serif;
        font-weight: 700;
        line-height: 1;
        font-size: 32px;
    }
</style>