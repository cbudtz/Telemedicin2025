<script>
	let userName = $state('');
	let password = $state('');
	const onclick = () => {
		if (userName === 'test' && password === 'test') {
			alert('You are logged in');
		} else {
			alert('You are not logged in');
		}
	};
</script>

<div class="text-2xl">This is a page with a plus sign in the URL</div>
<input
	type="text"
	class="rounded-md border border-gray-300 p-2"
	placeholder="Type something here"
	bind:value={userName}
/>
<input
	type="password"
	class="rounded-md border border-gray-300 p-2"
	placeholder="Type something here"
	bind:value={password}
/>
<button {onclick}>Click me</button>
