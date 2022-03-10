<script lang="ts">
	let users = [];
	let API_ROUTE = 'http://127.0.0.1:8000/users/';
	const getUsers = async () => {
		const res = await fetch(API_ROUTE);
		const data = await res.json();
		users = data['results'];
	};
</script>

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>
<button on:click={getUsers}>Get users</button>

{#each users as user}
	<p>{user.username}</p>
{/each}
