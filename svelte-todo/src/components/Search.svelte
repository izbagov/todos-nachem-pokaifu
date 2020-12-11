<script>
  export let todos;

  function addTodo(e) {
    const newTodo = {
      id: +new Date(),
      value: e.target.value,
      completed: false,
    };
    todos = [...todos, newTodo];
    e.target.value = "";
  }
</script>

<style>
  .search {
    margin-bottom: 20px;
  }

  input {
    width: 100%;
    border: 1px solid #ddd;
    font-size: 16px;
    padding: 15px 20px;
  }
</style>

<div class="search">
  <input
    type="text"
    on:change={addTodo}
    placeholder="Let's start search todo..." />
</div>
