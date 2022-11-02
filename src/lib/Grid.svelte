<svelte:options tag="base-grid" />

<div class="grid">
	<slot />
</div>

<style>
	.grid {
		font-family: 'Open Sans', sans-serif;
		position: relative;
		display: grid;
		width: 100%;
		grid-template-columns: repeat(4, 1fr);
		margin-inline: auto;
		max-width: 1440px;
	}

	@media (min-width: 640px) {
		.grid {
			grid-template-columns: repeat(4, 1fr);
		}
	}

	@media (min-width: 768px) {
		.grid {
			grid-template-columns: repeat(8, 1fr);
		}
	}

	@media (min-width: 1024px) {
		.grid {
			grid-template-columns: repeat(12, 1fr);
		}
	}

	@media (min-width: 1440px) {
		.grid {
			grid-template-columns: repeat(12, 1fr);
		}
	}
</style>
