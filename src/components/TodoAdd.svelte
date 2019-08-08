<script>
import { createEventDispatcher } from 'svelte'
const dispatch = createEventDispatcher()

let value = ''

function handleSubmit () {
  dispatch('create', value)
  value = ''
}
</script>

<style>
span {
  display: block;
}
</style>

<form on:submit|preventDefault={handleSubmit}>
  <label for="add">Add todo item</label>
  <span>
    <input id="add" bind:value>
    <button>+</button>
  </span>
</form>
