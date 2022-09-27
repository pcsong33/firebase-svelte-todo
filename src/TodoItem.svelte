<script lang="ts">

    import { createEventDispatcher } from 'svelte';

    const dispatch = createEventDispatcher();
    
    // helper function to remove task
    function remove() {
		dispatch('remove', { id });
	}

    // check toggle state
	function toggleStatus() {
        let newStatus = !complete;
		dispatch('toggle', {
            id,
            newStatus
        });
    }

    // define user id
    export let id = undefined;
    // define task name
    export let text = undefined;
    // define task status
    export let complete = undefined;
</script>

<style>
    .is-complete {
        text-decoration: line-through;
        color: green;
    }
</style>


<li>
<!-- mark the task with a green line if completed -->
{#if complete}
    <span class="is-complete">{ text }</span>
    <button on:click={toggleStatus}> ✔️ </button>
<!-- click x button to un-do a completed task   -->
{:else}
    <span>{ text }</span>
    <button on:click={toggleStatus}> ❌ </button>
{/if}

<!-- remove task if trash is clicked -->
<button on:click={remove}> 🗑 </button>

</li>