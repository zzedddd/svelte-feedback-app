<script>

	import FeedbackList from "./components/FeedbackList.svelte";
	import FeedbackStats from "./components/FeedbackStats.svelte";

	let review = [
		{
			id : 1,
			rating : 10,
			name : "Sylvia",
			feedback : "The box this comes in is 3 yard by 6 yard and weights 19 pound!!!"
		},
		{
			id : 2,
			rating : 9,
			name : "Jason",
			feedback : "My neighbor Lonnie has one of these. She works as a hobbit and she says it looks microscopic."
		},
		{
			id : 3,
			rating : 10,
			name : "Darya",
			feedback : "My co-worker Tyron has one of these. He says it looks stout."
		},
		{
			id : 4,
			rating : 8,
			name : "Reven",
			feedback : "i use it once a week when i'm in my firetruck."
		},
		{
			id : 5,
			rating : 10,
			name : "Megan",
			feedback : "Nam pretium turpis et arcu. Duis arcu tortor, suscipit eget, imperdiet nec, imperdiet iaculis, ipsum. Sed aliquam ultrices mauris. Integer ante arcu, accumsan a, consectetuer eget, posuere ut, mauris. Praesent adipiscing. Phasellus ullamcorper ipsum rutrum nunc. Nunc nonummy metus."
		}

	]
	const removeIt = (e) => {
		let itemId = e.detail;
		review = review.filter((item) => item.id != itemId);
	}

	$: count = review.length;
	$: avg = review.reduce((a, {rating}) => a + rating, 0)/count;
</script>

<main class="container">
	<FeedbackStats {count} {avg}/>
	<FeedbackList {review} on:remove-it = {removeIt} />
</main>

