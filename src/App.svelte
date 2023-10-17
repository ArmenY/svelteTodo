<script></script>

<main>
    <div class="todo__wrapper">
        <h1 class="todo__title">Your Todo List</h1>
        <button>Add ToDo</button>
            <div class="card__wrapper">
                <div class="todo__cardItem">
                        <p class="todo__cardDescription"></p>
                    <button>Delete todo</button>
                </div>
            </div>
    </div>
</main>

<style>
    body {
        padding: 0;
        margin: 0;
    }

    .todo__wrapper {
        width: 100%;
        height: 100%;
        background: #e4b45c;
    }

    .todo__title {
        text-align: center;
    }

    .card__wrapper {
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .todo__cardItem {
        padding: 30px;
        border: 1px solid green;
        border-radius: 4px;
    }
</style>