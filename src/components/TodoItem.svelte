<script>
import { createEventDispatcher } from 'svelte'
const dispatch = createEventDispatcher()

export let done
export let text

function handleDelete () {
  dispatch('delete')
}
</script>

<li>
  <input
    type="checkbox"
    aria-label={done ? `Todo “${text}” is done` : `Todo “${text}” isn't done`}
    bind:checked={done}
  >

  <input
    aria-label="Todo text"
    bind:value={text}
  >

  <button
    title="Delete “{text}”"
    type="button"
    on:click={handleDelete}
  >–</button>
</li>
