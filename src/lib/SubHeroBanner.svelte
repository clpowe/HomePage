<svelte:options tag="subhero-banner" />

<script lang="ts">
	type data = {
		subText: string
		text: string
		link: string
		ariaLabel: string
		hide: boolean
	}

	export let data = {} as data
</script>

<article class:hide={data.hide} class="[ hotspot-image hotspot-v2-container ]">
	<a href={data.link} aria-label={data.ariaLabel} class="content">
		<div>
			<p>{data.subText}</p>
			<p class="text">{data.text}</p>
		</div>
		<svg
			class="[ self-center ]"
			version="1.2"
			xmlns="http://www.w3.org/2000/svg"
			xmlns:xlink="http://www.w3.org/1999/xlink"
			overflow="visible"
			preserveAspectRatio="none"
			viewBox="0 0 26 26"
			width="35"
			height="35"
			fill="#FFF"
		>
			<g transform="translate(1, 1)">
				<path
					fill="inherit"
					d="m10.8788 17.657-1.41396-1.414 4.24196-4.243-4.24196-4.24298 1.41396-1.414 5.656 5.65698z"
					vector-effect="non-scaling-stroke"
				/>
			</g>
		</svg>
	</a>
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
	a {
		all: unset;
		cursor: pointer;
	}

	a:hover {
		text-decoration: none;
	}

	article {
		font-family: 'Open Sans', sans-serif;
		background-color: var(--ashley-black);
		color: #fff;
		width: 100%;
		padding-block: 1rem;
		padding-inline: 1rem;
		margin-bottom: 4rem;
	}

	.content {
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.content div {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding-block: 1rem;
	}

	p {
		max-width: 90ch;
		font-size: 1rem;
		line-height: 1.1;
		text-transform: uppercase;
		margin-inline: auto;
		text-align: center;
		font-weight: 400;
	}
	a {
		text-transform: lowercase;
	}

	.text {
		font-size: 1.5rem;
		text-transform: lowercase;
		font-weight: 700;
	}
	svg {
		margin-left: 0.5rem;
	}

	.hide {
		display: none;
	}
</style>
