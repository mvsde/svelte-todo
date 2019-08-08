<script>
import TodoAdd from './TodoAdd.svelte'
import TodoItem from './TodoItem.svelte'

let todos = [
  {
    done: false,
    text: 'Hello World!'
  },
  {
    done: true,
    text: 'Create an awesome JavaScript framework'
  }
]

function handleDelete (index) {
  todos.splice(index, 1)
  todos = todos
}

function handleCreate ({ detail }) {
  todos[todos.length] = {
    done: false,
    text: detail
  }
}
</script>

<ol>
  {#each todos as todo, i}
    <TodoItem
      bind:done={todo.done}
      bind:text={todo.text}
      on:delete={() => handleDelete(i)}
    />
  {/each}
</ol>

<TodoAdd on:create={handleCreate} />
