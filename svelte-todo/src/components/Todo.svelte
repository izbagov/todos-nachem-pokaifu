<script>
  export let todo, todos;

  function competeTodo() {
    const newTodos = todos.map((t) => {
      if (t.id === todo.id) {
        return {
          ...t,
          completed: !todo.completed,
        };
      }

      return t;
    });

    todos = [...newTodos];
  }

  function deleteTodo() {
    const newTodos = todos.filter((t) => t.id !== todo.id);

    todos = [...newTodos];
  }
</script>

<style>
  .todo {
    display: flex;
    border-bottom: 1px solid #ddd;
    padding-bottom: 5px;
    margin-bottom: 10px;
  }

  .todo.completed .text {
    text-decoration: line-through;
  }

  .text {
    flex: 1;
  }

  .delete {
    flex-shrink: 0;
    margin-left: 10px;
    border: 1px solid #eee;
    font-size: 12px;
    width: 22px;
    height: 22px;
    color: red;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    transition: border-color 0.2s ease-in-out;
  }

  .delete:hover {
    border-color: red;
  }
</style>

<div class="todo" class:completed={todo.completed}>
  <span class="text" on:click={competeTodo}>{todo.value}</span>
  <span class="delete" on:click={deleteTodo}>x</span>
</div>
