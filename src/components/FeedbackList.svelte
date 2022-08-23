<script>
    import FeedbackItem from "./FeedbackItem.svelte";
    export let review = []; 
</script>

{#each review as rv (rv.id) }
    <FeedbackItem item = {rv} on:remove-it/>
{/each}

