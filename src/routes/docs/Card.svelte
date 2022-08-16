<script>
	const PREFI_TITLE = 'Hello';
	let count = 0;

	function incrementCount() {
		count += 1;
	}
	$: doubled = count * 2;
	$: if (count >= 10) {
		alert('count is dangerously high!');
		count = 9;
	}
</script>

<div class="card">
	<h2>
		{PREFI_TITLE}
	</h2>
	<button on:click={incrementCount}>
		Clicked {count}
		{count === 1 ? 'time' : 'times'}
	</button>
	<p>{count} doubled is {doubled}</p>
</div>

<style>
</style>
