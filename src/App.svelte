<script>
    import Modal from "./Modal.svelte";
    import Card from "./Card.svelte";
    import TodoForm from "./TodoForm.svelte";
    let todoItems = [];

    let showModal = false
    const toggleModal = ()=> {
        showModal = !showModal
    }
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
        <h1 class="todo__title">Your Todo List</h1>
        <button on:click={toggleModal}>Add ToDo</button>
        <Card/>
    </div>
</main>

<style>
    body {
        padding: 0;
        margin: 0;
    }

    .todo__wrapper {
        width: 100vw;
        height: 100vh;
        background: #e4b45c;
    }

    .todo__title {
        text-align: center;
    }
</style>