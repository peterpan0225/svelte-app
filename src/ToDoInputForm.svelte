<script>
  import { toDoItems } from "./store.js"
  import { onMount } from "svelte";
  export let userName
  let newItem = ""
  let newItemInputFrom = null

  onMount(() => {
    newItemInputFrom.focus()
  })
  
  function addToList() {
    $toDoItems = [...$toDoItems, {text: newItem, status: false}]
    newItem = ""
  }
</script>
  
<input bind:value={newItem} bind:this={newItemInputFrom} type="text" placeholder="Add a new task">
<button on:click={addToList}>Add</button>

<h3>{userName}'s task list:</h3>