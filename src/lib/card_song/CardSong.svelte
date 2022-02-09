<script lang="ts">
	import IoIosArrowForward from 'svelte-icons/io/IoIosArrowForward.svelte';
	import IoIosArrowBack from 'svelte-icons/io/IoIosArrowBack.svelte';
	import Slider from '@smui/slider';

	export let isActive: boolean;

	let value = 0;
</script>

<div class="card">
	<div class="song" />

	{#if isActive}
		<div class="controllers">
			<div class="button-wrapper back">
				<button>
					<IoIosArrowBack />
				</button>
			</div>

			<div>
				<Slider style="margin: 0;" bind:value min={-10} max={10} step={0.001} />
			</div>

			<div class="button-wrapper forward">
				<button>
					<IoIosArrowForward />
				</button>
			</div>
		</div>
	{/if}
</div>

<style>
	.card {
		width: 100%;
	}

	.song {
		width: 100%;
		height: 10rem;
		background-color: var(--gray-700);
		border-radius: 10px;
		margin-bottom: 0.5rem;
	}

	.button-wrapper {
		display: flex;
		align-items: center;
	}

	.back {
		justify-content: flex-start;
	}

	.forward {
		justify-content: flex-end;
	}

	button {
		background: var(--gray-700);
		border: none;
		border-radius: 50%;
		width: 2rem;
		height: 2rem;
		display: flex;
		align-items: center;
		justify-content: center;
		color: var(--gray-300);
		cursor: pointer;
		transition: 0.5s;
	}

	button:hover {
		background: var(--gray-800);
	}

	.controllers {
		display: grid;
		grid-template-columns: 2rem 2fr 2rem;
		align-items: center;
		grid-gap: 1rem;
	}
</style>
