<svelte:options tag="feature-section" />

<script lang="ts">
	type item = {
		id: number
		img: string
		text: string
		price: string
		ariaLabel: string
		link: string
	}

	type Data = {
		title: string
		linkText: string
		link: string
		image: string
		altText: string
		ariaLabel: string
	}

	export let data = {} as Data
	export let items: item[] = []
</script>

<article class="">
	<h2>{data.title}</h2>
	<div class="feature">
		<img src={data.image} alt="" loading="lazy" />
		<div class="link">
			<base-link
				text={data.linkText}
				href={data.link}
				aria-label={data.ariaLabel}
			/>
		</div>
	</div>

	<div class="items-container">
		{#each items as item}
			<div class="item">
				<img src={item.img} alt="" loading="lazy" />
				<div class="content hotspot-image hotspot-v2-container">
					<base-link
						class="finance-dk2-pq"
						text={item.text}
						href={item.link}
						aria-label={item.ariaLabel}
					/>
				</div>
			</div>
		{/each}
	</div>
</article>

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

	:where(:not(dialog)) {
		margin: 0;
	}

	:where(a):where(:not(:hover)) {
		text-decoration: inherit;
	}

	:where(a[href]):visited {
		color: var(--link-visited);
	}

	:where(img, svg) {
		display: block;
		block-size: auto;
		max-inline-size: 100%;
	}

	article {
		font-family: 'Open Sans', sans-serif;
		display: grid;
		max-width: 1440px;
		margin-inline: auto;
		gap: 1rem;
		margin-bottom: 6rem;
		padding-inline: 1rem;
	}

	h2 {
		grid-column: 1 / -1;
		font-family: 'Open Sans', sans-serif;
		text-transform: lowercase;
		font-weight: 700;
		font-size: clamp(28px, 4vw, 36px);
		line-height: 2.25rem;
	}

	.feature {
		display: flex;
		flex-direction: column;
		gap: 1rem;
		grid-column: span 2;
	}

	.feature > img {
		max-inline-size: 100%;
		width: auto;
		max-height: 750px;
		object-fit: cover;
		flex-grow: 1;
	}
	.feature > .link {
		background-color: var(--gray-1);
		display: flex;
		justify-content: flex-end;
		padding: 0.5rem;
	}

	.items-container {
		display: grid;
		grid-auto-flow: column;
		overflow-x: auto;
		scroll-behavior: smooth;
		overscroll-behavior-inline: contain;
		gap: 1rem;
	}
	.item {
		position: relative;
		display: flex;
		width: 300px;
		align-items: center;
		padding: 1rem;
		gap: 1rem;
		background-color: var(--gray-1);
	}

	.item > img {
		max-inline-size: 100%;
		height: 80px;
		max-height: 210px;
	}
	.content {
		display: flex;
		flex-direction: column;
	}
	.content p {
		font-weight: 700;
	}
	/* .item > base-link {
		position: relative;
	} */

	@media (min-width: 1020px) {
		article {
			display: grid;
			grid-template-columns: 1fr 1fr 1fr;
		}

		.items-container {
			display: grid;
			grid-auto-flow: row;
			gap: 1rem;
		}

		.item {
			position: relative;
			display: flex;
			width: auto;
			align-items: center;
			padding: 1rem;
			gap: 1rem;
			background-color: var(--gray-1);
		}

		.item > img {
			max-inline-size: 100%;
			height: auto;
			max-height: 210px;
		}

		.content > base-link {
			position: absolute;
			right: 1rem;
			bottom: 1rem;
		}
	}
</style>
