<script>

	import FeedbackList from "./components/FeedbackList.svelte";
	import FeedbackStats from "./components/FeedbackStats.svelte";

	let review = [
		{
			id : 1,
			rating : 10,
			name : "Sylvia",
			feedback : "Fuck yeah daddy! Fuck my pussy harder harder and harder!"
		},
		{
			id : 2,
			rating : 9,
			name : "Jason",
			feedback : "Boom bitch! i love this!"
		},
		{
			id : 3,
			rating : 10,
			name : "Darya",
			feedback : "Fuck yeah daddy! Fuck my pussy harder harder and harder! I love it, its so good yummmmmmm"
		},
		{
			id : 4,
			rating : 8,
			name : "Reven",
			feedback : "Witch said MC I'm not even close to witch"
		},
		{
			id : 5,
			rating : 10,
			name : "Megan",
			feedback : "My pussy is so wet! Please fill it with your cum daddy please please please please please!"
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

