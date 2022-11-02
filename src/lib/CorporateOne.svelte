<svelte:options tag="corporate-one" />

<script lang="ts">
	type item = {
		id: number
		icon: string
		title: string
		text: string
		link: string
		ariaLabel: string
	}
	export let data: item[] = []
</script>

<section>
	<div class="home-content corporate-one">
		{#each data as item}
			<div
				class="
              corporate-one__item
              text-center
              [
              hotspot-image hotspot-v2-container
              ]
            "
				style="text-align: center"
			>
				<img src={item.icon} alt="" loading="lazy" />
				<h3>{item.title}</h3>
				<p class="margin-inline">{item.text}</p>
				<a href={item.link} aria-label={item.ariaLabel}>learn more</a>
			</div>
		{/each}
	</div>
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

	:where(:not(dialog)) {
		margin: 0;
	}

	:where(a):where(:not(:hover)) {
		text-decoration: inherit;
	}

	:where(a[href]):visited {
		color: var(--link-visited);
	}

	a {
		font-family: 'Open Sans', sans-serif;
		color: #000;
		justify-content: start;
		text-decoration: none;
		letter-spacing: 3px;
		cursor: pointer;
		display: flex;
		align-items: center;
		justify-content: flex-start;
		text-transform: uppercase;
		letter-spacing: 1.2px;
		background-color: transparent;
		text-align: center;
		margin-inline: auto;
	}

	a:hover {
		color: var(--gray-6);
	}

	.corporate-one {
		font-family: 'Open Sans', sans-serif;
		display: grid;
		gap: 1rem;
		text-align: center;
		margin-bottom: 6rem;
		max-width: 1440px;
		margin-inline: auto;
	}

	.corporate-one__item {
		text-align: center;
		padding: var(--font-size-fluid-1) var(--font-size-fluid-2);
		display: flex;
		flex-direction: column;
		gap: 1rem;
		justify-items: center;
	}

	h3 {
		font-weight: 700;
	}

	.corporate-one__item p {
		max-width: 35ch;
		margin-inline: auto;
	}

	.corporate-one__item > img {
		width: 72px;
		margin-inline: auto;
	}

	@media (min-width: 768px) {
		.corporate-one {
			display: grid;
			grid-template-columns: repeat(3, 1fr);
			gap: 1rem;
		}
	}
</style>
