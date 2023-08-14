<script lang="ts">
  import Todo from "$lib/components/Todo.svelte";
  let todos: any[] = [];
  let todoText = '';
  let id = 0;
  const createtodo = (text: string) => ({text: text, done: false, id: ++id});

  function todoToggle(todo: any) {
    const { id } = todo;
    todos = todos.map(t => id === t.id ? {...t, done: !t.done} : t); 
  }

  function addTodo() {
    todos.push(createtodo(todoText));
    todos = todos;
    todoText = '';
  }

  function deleteTodo(todo: any) {
    const { id } = todo;
    todos = todos.filter((t) => t.id != id);
  }
</script>

<form on:submit|preventDefault={addTodo}>
  <input
      size="30"
      placeholder="Place new todo here"
      bind:value={todoText} />
  <button disabled={todoText === ''}>Add</button>
</form>

{#each todos as todo} 
  <Todo {...todo} on:toggle={() => todoToggle(todo)} on:delete={() => deleteTodo(todo)}/>
{/each}
