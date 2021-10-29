<script>
	export let content;
	export let createdTimestamp;
	export let displayName;
	export let avatarURL;
	export let attachmentURLs
</script>

<div class="message">
	<img class="avatar" src="{avatarURL}" alt="profile picture for {displayName}">
	<div>
		<span class="name">{displayName}</span>
		<span class="date">{new Date(createdTimestamp).toLocaleString()}</span>
		<p>{content}</p>
		{#each attachmentURLs as attachmentURL}
			<img src="{attachmentURL}" alt="attachment">
		{/each}
	</div>
</div>

<style>
	.avatar {
		border-radius: 100%;
		height: 3rem;
		margin-right: .5rem;
	}
	.name {
		color: var(--pure-white);
	}
	.date {
		margin-left: .25rem;
		color: var(--text-muted);
		font-size: .75rem
	}
	.message {
		display: flex;
		margin: .5rem;
		padding: .5rem;
		color: var(--text-normal);
	}
	p {
		margin: .5rem 0;
	}
	div {
		border-radius: 1em;
	}
	img {
		max-width: 100%;
	}
</style>