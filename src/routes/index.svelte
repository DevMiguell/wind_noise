<script context="module" lang="ts">
	export const prerender = true;
	import CardSong from '$lib/card_song/CardSong.svelte';

	const Cards = [
		{
			id: 1,
			is_active: true
		},
		{
			id: 2,
			is_active: false
		},
		{
			id: 3,
			is_active: false
		},
		{
			id: 4,
			is_active: false
		}
	];
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<section>
	<div class="cards_songs">
		{#each Cards as card}
			<CardSong isActive={card.is_active} />
		{/each}
	</div>
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 1;
	}

	.cards_songs {
		margin-top: 1rem;
		width: 100%;
		display: grid;
		justify-content: center;
		grid-template-columns: repeat(auto-fill, minmax(13rem, 1fr));
		grid-gap: 2rem;
	}
</style>
