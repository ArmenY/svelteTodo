<script>
    export let todoItems = [];
    const deleteTodo = (id) => {
        todoItems = todoItems.filter((todoItem) => id !== todoItem.id)
        console.log(todoItems)
    }
</script>

<div class="card__wrapper">
    {#each todoItems as todoItem (todoItem.id)}

        <div class="todo__cardItem">
            {#if todoItem.todoTitle}
                <p class="todo__title">{todoItem.todoTitle}</p>
            {:else}
                <p class="todo__title">No Title</p>
            {/if}
            {#if todoItem.todoDescription}
                <p class="todo__cardDescription">{todoItem.todoDescription}</p>
            {:else}
                <p class="todo__cardDescription">No Description</p>
            {/if}
            <button class="card__deleteBtn" on:click={() => deleteTodo(todoItem.id)}>Delete todo</button>
        </div>
    {/each}

</div>

<style>
    .card__wrapper {
        display: flex;
        align-items: center;
        justify-content: flex-start;
        flex-wrap: wrap;
    }

    .card__deleteBtn {
        align-self: flex-end;
    }

    .todo__cardItem {
        width: 100%;
        max-width: 250px;
        margin: 20px;
        padding: 30px;
        border: 1px solid #008000;
        border-radius: 4px;
    }

    .todo__title {
        font-family: sans-serif;
        font-size: 20px;
        font-weight: 700;
        line-height: 1.5;
    }

    .todo__cardDescription {
        font-family: sans-serif;
        font-size: 16px;
        font-weight: 500;
        line-height: 1.5;
    }

    .card__deleteBtn {
        margin-top: 25px;
        margin-right: 0;
        font-family: sans-serif;
        font-size: 16px;
        font-weight: 600;
        color: #fff;
        background: #e4b45c;
    }
</style>