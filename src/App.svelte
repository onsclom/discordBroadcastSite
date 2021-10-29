<script>
	import { onMount } from 'svelte';
	import DiscordMessage from './DiscordMessage.svelte'

	let messages = [];


	onMount(async () => {
		const res = await fetch(`https://discord-broadcast.herokuapp.com/`);
		messages = await res.json();
	});
</script>

<main>
	<h1>discord broadcast 📣</h1>
	{#each messages as message}
		<DiscordMessage {...message}/>
	{/each}
</main>

<style>
	h1 {
		font-color: var(--pure-white);
	}
	main {
		margin: auto;
		max-width: 40em;
	}
</style>