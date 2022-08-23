<script>
    export let count;
    export let avg;
</script>

<div class="feedback-stats">
    <h1> Reviews: {count}</h1>
    <h1> Average: {avg}</h1>
</div>

<style>
    .feedback-stats{
        display: flex;
        justify-content: space-between;
        align-items: center;
        color: aqua;
        font-size: x-small;
    }
</style>