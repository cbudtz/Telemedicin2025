<script>
	import Title from '$lib/components/Title.svelte';
	import Link from '$lib/components/Link.svelte';
	import H1 from '$lib/components/H1.svelte';

	let username = $state('user');
	let password = $state('password');

	const createUser = async () => {
		const response = await fetch('/api/user', {
			method: 'POST',
			headers: {
				'Content-Type': 'application/json'
			},
			body: JSON.stringify({ username, password })
		});
		await response.json();
		if (response.ok) {
			alert('Bruger oprettet!');
		} else {
			alert('Fejl ved oprettelse af bruger!');
		}
		username = '';
		password = '';
	};
</script>

<Title>Administration</Title>

<div class="my-4">
	<H1>Brugeradministration</H1>
	<p>Her kan du oprette nye brugere til systemet.</p>
</div>

<div class="mb-4">
	<input id="username" type="text" bind:value={username} placeholder="Indtast brugernavn" class="input" />
</div>
	
<div class="mb-4">
	<input id="password" type="password" bind:value={password} placeholder="Indtast adgangskode" class="input" />
</div>
	
<div class="mb-4">
	<button class="btn btn-primary" onclick={createUser}>Opret ny bruger</button>
</div>

<div class="mt-4">
	<Link href="/diary">Tilbage til dagbog</Link>
</div>

