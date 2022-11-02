<svelte:options tag="instock-ready" />

<script lang="ts">
	export let items: any
	export let light: boolean

	type Item = {
		id: number
		eyebrow: string
		headline: string
		headlineSuperScript: string //
		link: string
		ariaLabel: string
		linkText: string
		image: string
		light: boolean
	}

	type Data = Item[]

	export let data = [] as Data
</script>

<section>
	{#each data as item}
		<div class="container [ hotspot-image hotspot-v2-container ]">
			<a href={item.link} aria-label={item.ariaLabel} class="img-container">
				<img src={item.image} alt="" loading="lazy" />
				<div class="content" class:color={item.light}>
					<p class="eyebrow">{item.eyebrow}</p>
					<p class="header">
						{item.headline}<sup>{item.headlineSuperScript}</sup>
					</p>
				</div>
			</a>
			<base-link
				text={item.linkText}
				href={item.link}
				ariaLabel={item.ariaLabel}
			/>
		</div>
	{/each}
</section>

<style>
	html {
		box-sizing: border-box;
		font-size: 16px;
	}

	*,
	*:before,
	*:after {
		box-sizing: inherit;
	}

	body,
	h1,
	h2,
	h3,
	h4,
	h5,
	h6,
	p,
	ol,
	ul {
		margin: 0;
		padding: 0;
		font-weight: normal;
	}

	ol,
	ul {
		list-style: none;
	}

	img {
		max-width: 100%;
		height: auto;
	}

	a {
		all: unset;
		cursor: pointer;
	}

	section {
		font-family: 'Open Sans', sans-serif;
		max-width: 1440px;
		display: flex;
		margin-inline: auto;
		flex-direction: column;
		gap: 2rem;
		margin-bottom: 6rem;
		padding-inline: 1rem;
	}

	.container {
		width: 100%;
		height: auto;
		display: flex;
		flex-direction: column;
		align-items: flex-end;
		gap: 1rem;
	}

	.img-container {
		width: 100%;
		height: 250px;
		overflow: hidden;
		position: relative;
		display: grid;
		place-content: center;
	}

	img {
		height: 100%;
		width: 100%;
		object-fit: cover;
		position: absolute;
	}

	.content {
		text-align: center;
		z-index: 1;
	}

	.eyebrow {
		font-family: 'Open Sans';
		font-style: normal;
		font-weight: 400;
		font-size: clamp(0.8rem, 2vw, 1rem);
		line-height: 16px;

		text-align: center;
		letter-spacing: 0.08em;
		text-transform: uppercase;
	}

	.header {
		font-family: 'Open Sans';
		font-style: normal;
		font-weight: 700;
		font-size: clamp(1.5rem, 3vw, 2rem);
		text-align: center;
	}

	@media (min-width: 768px) {
		section {
			max-width: 1440px;
			display: flex;
			margin-inline: auto;
			flex-direction: row;
			gap: 2rem;
		}
		.img-container {
			height: 200px;
		}
		img {
			object-fit: cover;
			position: absolute;
		}
	}
	@media (min-width: 1024px) {
		.img-container {
			height: 350px;
		}
	}

	.color {
		color: #fff;
		fill: #fff;
	}
</style>
