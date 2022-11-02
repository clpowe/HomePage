<svelte:options tag="deals-slider" />

<script lang="ts">
	import { afterUpdate } from 'svelte'

	type Deals = Deal[]

	type Deal = {
		deal: string
		change: string
		linkText: string
		arialabel: string
		link: string
	}

	export let data = [] as Deals

	let scroller = null
	let container = null

	let cw = null
	let sw = null

	let end = true
	let start = false

	afterUpdate(() => {
		const maxScrollLeft = scroller.scrollWidth - scroller.clientWidth
		if (cw > sw) {
			end = false
		} else {
			end = true
		}
		if (scroller.scrollLeft === maxScrollLeft) {
			end = false
		} else {
			end = true
		}
	})

	const handleScroll = () => {
		const maxScrollLeft = scroller.scrollWidth - scroller.clientWidth

		if (scroller.scrollLeft <= 1) {
			start = false
		} else {
			start = true
		}

		if (scroller.scrollLeft === maxScrollLeft) {
			end = false
		} else {
			end = true
		}
	}

	let scrollRight

	const handleRightClick = () => {
		scroller.scrollBy({
			top: 100,
			left: 200,
			behavior: 'smooth'
		})
	}

	const stopRight = () => {
		clearInterval(scrollRight)
	}

	let scrollLeft

	const handleLeftClick = () => {
		scroller.scrollBy(-200, 0)
		// scrollLeft = setInterval(() => {}, 1)
	}

	const stopLeft = () => {
		clearInterval(scrollLeft)
	}
</script>

<section class="section-slider">
	<base-grid>
		<div class="container" bind:this={container} bind:clientWidth={cw}>
			{#if end}
				<div
					class="slider-right "
					on:mousedown={handleRightClick}
					on:mouseup={stopRight}
				>
					<svg
						width="8"
						height="12"
						viewBox="0 0 8 12"
						fill="#fff"
						xmlns="http://www.w3.org/2000/svg"
					>
						<path
							d="M1.87884 11.657L0.464844 10.243L4.70684 6L0.464844 1.75702L1.87884 0.343018L7.53484 6L1.87884 11.657Z"
							fill="inherit"
						/>
					</svg>
				</div>
			{/if}
			{#if start}
				<div
					class="slider-left "
					on:mousedown={handleLeftClick}
					on:mouseup={stopLeft}
				>
					<svg
						width="8"
						height="12"
						viewBox="0 0 8 12"
						fill="#fff"
						xmlns="http://www.w3.org/2000/svg"
					>
						<path
							d="M1.87884 11.657L0.464844 10.243L4.70684 6L0.464844 1.75702L1.87884 0.343018L7.53484 6L1.87884 11.657Z"
							fill="inherit"
						/>
					</svg>
				</div>
			{/if}
			<ul
				class="media-scroller "
				bind:this={scroller}
				bind:offsetWidth={sw}
				on:scroll={handleScroll}
			>
				{#each data as deal}
					<li class="media-element hotspot-image hotspot-v2-container ">
						<a class="deal" href={deal.link} aria-label={deal.arialabel}>
							<p>{deal.deal}<sup>{deal.change}</sup></p>
							<base-link text={deal.linkText} small={true} light={true} />
						</a>
					</li>
				{/each}
			</ul>
		</div>
	</base-grid>
</section>

<style lang="scss">
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

	a {
		all: unset;
		cursor: pointer;
	}

	a:hover {
		text-decoration: underline;
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

	.section-slider {
		position: relative;
		margin-inline: auto;
		color: var(--ashley-black);
		margin-bottom: 6rem;
		padding-inline: 0rem;
	}

	@media (min-width: 640px) {
		.section-slider {
			padding-inline: 1rem;
		}
	}

	@media (min-width: 1440px) {
		.section-slider {
		}
	}

	::-webkit-scrollbar {
		width: 5px;
	}

	::-webkit-scrollbar-thumb {
		background: var(--ashley-black);
	}

	::-webkit-scrollbar-thumb:hover {
		background: #555;
	}

	.media-scroller::-webkit-scrollbar:horizontal {
		-webkit-appearance: none;
		height: 6px;
	}

	.container {
		position: relative;
		grid-column: 1/-1;
		min-width: 0;
	}

	.media-scroller {
		--size: 296px;
		--gap: 2rem;

		display: inline-grid;
		grid-auto-flow: column;
		gap: calc(var(--gap) / 2);
		margin: 0;
		max-width: 100%;
		scroll-behavior: smooth;

		padding-inline-end: var(--gap);
		padding-block-start: calc(var(--gap) / 2);
		padding-block-end: calc(var(--gap) / 2);

		overflow-x: auto;
		overscroll-behavior-inline: contain;
		scroll-snap-type: inline mandatory;
		scroll-padding-left: var(--gap);
		scroll-padding-right: var(--gap);
		scroll-padding-inline: var(--gap);
		padding-right: 0;

		& a {
			text-align: center;
			display: inline-block;
			text-decoration: none;
			background-color: #3b4758;
			color: inherit;
			outline-offset: 12px;

			&:focus {
				outline-offset: 7px;
			}

			@media (prefers-reduced-motion: no-preference) {
				transition: outline-offset 0.25s ease;
			}
		}

		& > li {
			display: inline-block;

			&:last-of-type figure {
				position: relative;
			}
		}
		& figure {
			scroll-snap-align: start;

			& figcaption {
				text-transform: lowercase;
			}
		}

		& a {
			display: inline-block;
			text-decoration: none;
			color: inherit;
			outline-offset: 12px;
			width: var(--size);

			&:focus {
				outline-offset: 7px;
			}

			@media (prefers-reduced-motion: no-preference) {
				transition: outline-offset 0.25s ease;
			}
		}
		@supports (aspect-ratio: 1) {
			.media-scroller figure > picture {
				inline-size: auto;
				aspect-ratio: 1;
			}
		}
		img {
			object-fit: contain;
			width: var(--size);
		}
	}

	picture {
		max-inline-size: 200px;
	}

	figure {
		text-align: start;
	}

	figure p {
		font-weight: 700;
	}

	.content {
		display: flex;
		flex-direction: column;
		margin-right: 1rem;
		justify-content: center;
		grid-column: 1/-1;
	}

	.header {
		font-size: 20px;
		font-weight: 700;
		margin-bottom: 1rem;
		line-height: 120%;
		max-width: 100%;
	}

	.subheader {
		display: none;
		max-width: 25ch;
	}

	.slider-right {
		background-color: var(--ashley-black);
		height: 48px;
		width: 48px;
		color: #f4f4f4;
		display: none;
		place-content: center;
		position: absolute;
		right: 0;
		top: calc(50% - 24px);
		cursor: pointer;
		z-index: 4;
	}

	.slider-left {
		background-color: var(--ashley-black);
		height: 48px;
		width: 48px;
		color: #f4f4f4;
		display: none;
		place-content: center;
		position: absolute;
		left: 0;
		top: calc(50% - 24px);
		transform: scale(-1);
		cursor: pointer;
		z-index: 4;
	}
	.slider-right:hover {
		background-color: #525252;
	}

	.slider-left:hover {
		background-color: #525252;
	}

	.hide {
		opacity: 0;
	}

	.show {
		opacity: 1;
	}

	@media (min-width: 640px) {
		.header {
			font-size: 30px;
		}
	}

	@media (min-width: 768px) {
		.slider-right {
			display: grid;
		}

		.slider-left {
			display: grid;
		}
		.content {
			grid-column: span 2;
		}
		.header {
			font-size: 30px;
			max-width: 10ch;
		}
		.subheader {
			display: block;
		}

		.container {
			grid-column: 1/-1;
		}
	}

	@media (min-width: 1024px) {
		.content {
			grid-column: span 3;
		}

		.header {
			font-size: 44px;
			grid-column: span 1/3;
		}

		.container {
			grid-column: 1/-1;
		}
	}
	@media (min-width: 1440px) {
		.content {
			grid-column: span 2;
		}

		.container {
			grid-column: 1/-1;
		}
	}

	.deal {
		padding-inline: 1rem;
		padding-block: 1.25rem;
	}

	p {
		text-align: start;
		color: #f7ac8e;
		font-weight: 700;
		font-size: 28px;
		line-height: 36px;
		margin-bottom: 0.25em;
	}
	sup {
		font-size: 0.55em;
	}
</style>
