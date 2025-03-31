<script>
	import { goto } from '$app/navigation';
	import Button from '$lib/Button.svelte';

	let userName = $state('');
	let password = $state('');

	const btnclick = () => {
		if (userName === 'admin' && password === 'admin') {
			goto('/home');
		} else {
			alert('Login failed');
		}
	};
</script>

<div>
	<input bind:value={userName} placeholder="Brugernavn" />
</div>
<div>
	<input bind:value={password} placeholder="Kodeord" />
</div>
<div>
	<button onclick={btnclick}>Login</button>
</div>
