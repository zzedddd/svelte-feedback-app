<script>
    import { createEventDispatcher } from "svelte"
    import Card from "./Card.svelte";
    export let item;
    let dispach = createEventDispatcher();
    export const removeItem = (itemId) => { 
        dispach("remove-it", itemId);
    };
</script>
<Card>
    <div class="num-display">
        {item.rating}
    </div>
    <button class="close" on:click={removeItem(item.id)}>X</button>
    <p class="text-display">
        {item.feedback}
    </p>
    <div class="name-display">
        {item.name}
    </div>
</Card>

<style>
    .num-display {
        position: absolute;
        top: -10px;
        left: -10px;
        width: 25px;
        height: 25px;
        background: linear-gradient(-45deg, #23d5ab, #23a6d5);
	    background-size: 400% 400%;
	    animation: gradient 10s ease infinite;
        color: #fff;
        border: 1px #eee solid;
        border-radius: 50%;
        padding: 10px;
        text-align:center;
        vertical-align: middle;
        font-size: 20px;
    }
    .name-display {
        position: absolute;
        bottom: 5px;
        left: 5px;
        width: 100px;
        height: 15px;
        background: linear-gradient(-45deg, #23a6d5, #23d5ab);
	    background-size: 400% 400%;
	    animation: gradient 10s ease infinite;
        color: #fff;
        border: 0px #eee transparent;
        border-radius: 15px;
        padding: 10px;
        text-align:center;
        vertical-align: middle;
        font-size: 15px;
    }
    .close {
        position: absolute;
        top: 10px;
        right: 10px;
        cursor: pointer;
        border: none;
        background: none;
        
    }
</style>
