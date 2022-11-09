<svelte:options tag="financing-section" />

<script lang="ts">
	type Data = {
		image: string
		eyebrow: string
		headline: string
		headlineSuperScript: string
		details: string
		mobilelink: string
		desktoplink: string
		linkText: string
		ariaLabel: string
		detailsLink: string
		detailsariaLabel: string
	}

	export let data = {
		image: '',
		eyebrow: '',
		headline: '',
		headlineSuperScript: '',
		details: '',
		mobilelink: '',
		desktoplink: '',
		linkText: '',
		ariaLabel: '',
		detailsLink: '',
		detailsariaLabel: ''
	} as Data

	function handleClick(href) {
		window.open(href, 'targetWindow', 'width=500, height=500')
	}
</script>

<section>
	<article class="[ hotspot-image hotspot-v2-container ]">
		<svg
			class="card"
			version="1.2"
			xmlns="http://www.w3.org/2000/svg"
			xmlns:xlink="http://www.w3.org/1999/xlink"
			overflow="visible"
			preserveAspectRatio="none"
			viewBox="0 0 56.314998626708984 48"
			height="54"
			width="63"
		>
			<g transform="translate(1, 1)">
				<defs>
					<clipPath
						id="clip-path_1656005520628"
						vector-effect="non-scaling-stroke"
					>
						<rect
							fill="none"
							transform="translate(-2 -2)"
							height="46"
							width="54.315"
							id="Rectangle_261848_1656005520628"
							vector-effect="non-scaling-stroke"
						/>
					</clipPath>
				</defs>
				<g transform="translate(2 2)" id="Group_302483_1656005520628">
					<rect
						fill="#333"
						transform="translate(44.291 34.68)"
						height="1.707"
						width="0.777"
						id="Rectangle_261832_1656005520628"
						vector-effect="non-scaling-stroke"
					/>
					<rect
						fill="#333"
						transform="translate(42.227 34.68)"
						height="1.707"
						width="0.777"
						id="Rectangle_261833_1656005520628"
						vector-effect="non-scaling-stroke"
					/>
					<rect
						fill="#333"
						transform="translate(40.163 34.68)"
						height="1.707"
						width="0.777"
						id="Rectangle_261834_1656005520628"
						vector-effect="non-scaling-stroke"
					/>
					<rect
						fill="#333"
						transform="translate(38.1 34.68)"
						height="1.707"
						width="0.777"
						id="Rectangle_261835_1656005520628"
						vector-effect="non-scaling-stroke"
					/>
					<rect
						fill="#333"
						transform="translate(34.954 34.68)"
						height="1.707"
						width="0.777"
						id="Rectangle_261836_1656005520628"
						vector-effect="non-scaling-stroke"
					/>
					<rect
						fill="#333"
						transform="translate(32.89 34.68)"
						height="1.707"
						width="0.777"
						id="Rectangle_261837_1656005520628"
						vector-effect="non-scaling-stroke"
					/>
					<rect
						fill="#333"
						transform="translate(30.826 34.68)"
						height="1.707"
						width="0.777"
						id="Rectangle_261838_1656005520628"
						vector-effect="non-scaling-stroke"
					/>
					<rect
						fill="#333"
						transform="translate(28.763 34.68)"
						height="1.707"
						width="0.777"
						id="Rectangle_261839_1656005520628"
						vector-effect="non-scaling-stroke"
					/>
					<rect
						fill="#333"
						transform="translate(25.616 34.68)"
						height="1.707"
						width="0.777"
						id="Rectangle_261840_1656005520628"
						vector-effect="non-scaling-stroke"
					/>
					<rect
						fill="#333"
						transform="translate(23.553 34.68)"
						height="1.707"
						width="0.777"
						id="Rectangle_261841_1656005520628"
						vector-effect="non-scaling-stroke"
					/>
					<rect
						fill="#333"
						transform="translate(21.489 34.68)"
						height="1.707"
						width="0.777"
						id="Rectangle_261842_1656005520628"
						vector-effect="non-scaling-stroke"
					/>
					<rect
						fill="#333"
						transform="translate(19.426 34.68)"
						height="1.707"
						width="0.777"
						id="Rectangle_261843_1656005520628"
						vector-effect="non-scaling-stroke"
					/>
					<rect
						fill="#333"
						transform="translate(16.28 34.68)"
						height="1.707"
						width="0.777"
						id="Rectangle_261844_1656005520628"
						vector-effect="non-scaling-stroke"
					/>
					<rect
						fill="#333"
						transform="translate(14.216 34.68)"
						height="1.707"
						width="0.777"
						id="Rectangle_261845_1656005520628"
						vector-effect="non-scaling-stroke"
					/>
					<rect
						fill="#333"
						transform="translate(12.152 34.68)"
						height="1.707"
						width="0.777"
						id="Rectangle_261846_1656005520628"
						vector-effect="non-scaling-stroke"
					/>
					<rect
						fill="#333"
						transform="translate(10.089 34.68)"
						height="1.707"
						width="0.777"
						id="Rectangle_261847_1656005520628"
						vector-effect="non-scaling-stroke"
					/>
					<g id="Group_302482_1656005520628">
						<g
							clip-path="url(#clip-path_1656005520628)"
							id="Group_302481_1656005520628"
						>
							<path
								stroke-width="0.5"
								stroke="#333"
								fill="#333"
								transform="translate(-24.241 -57.037)"
								d="M69.241,70.779H34.4A4.321,4.321,0,0,0,30.082,75.1V94.721A4.321,4.321,0,0,0,34.4,99.037H69.241a4.321,4.321,0,0,0,4.316-4.316V75.1a4.321,4.321,0,0,0-4.316-4.316M72.78,94.721a3.543,3.543,0,0,1-3.539,3.539H34.4a3.543,3.543,0,0,1-3.539-3.539V92.639h0V75.1A3.543,3.543,0,0,1,34.4,71.556H69.241A3.544,3.544,0,0,1,72.78,75.1Z"
								id="Path_423877_1656005520628"
								vector-effect="non-scaling-stroke"
							/>
							<path
								stroke-width="0.5"
								stroke="#323332"
								fill="#333"
								transform="translate(0 0)"
								d="M5.064,29.8,2.718,21.044l2.346-.629v-.8l-2.547.682L1.165,15.251,41.658,4.4l1.351,5.044L29.868,12.966h3l10.342-2.771.742,2.771h.8L42.141,3.2A4.316,4.316,0,0,0,36.855.149L3.2,9.166A4.32,4.32,0,0,0,.147,14.452L5.064,32.8ZM.9,14.251A3.543,3.543,0,0,1,3.4,9.916L37.056.9a3.54,3.54,0,0,1,4.335,2.5l.067.249L.964,14.5Z"
								id="Path_423878_1656005520628"
								vector-effect="non-scaling-stroke"
							/>
						</g>
					</g>
				</g>
			</g>
		</svg>
		<div class="wrapper">
			<div class="main">
				<p class="eyebrow">{data.eyebrow}</p>
				<h2 class="maintext">
					{data.headline}<sup>{data.headlineSuperScript}</sup>
				</h2>
			</div>

			<p class="legalText">
				{data.details}
				<a
					class="link"
					href={data.detailsLink}
					aria-label={data.detailsariaLabel}>Learn More</a
				>
			</p>

			<div class="mobile">
				<!-- svelte-ignore a11y-missing-attribute -->
				<a
					class="finance-dk2-pq"
					aria-label={data.ariaLabel}
					on:click={handleClick(data.mobilelink)}
					>{data.linkText}
					<svg
						version="1.2"
						xmlns="http://www.w3.org/2000/svg"
						xmlns:xlink="http://www.w3.org/1999/xlink"
						overflow="visible"
						preserveAspectRatio="none"
						viewBox="0 0 26 26"
						width="24"
						height="24"
						fill="inherit"
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
			</div>
			<div class="desktop">
				<!-- svelte-ignore a11y-missing-attribute -->
				<a
					class="finance-dk2-pq"
					aria-label={data.ariaLabel}
					on:click={handleClick(data.desktoplink)}
					>{data.linkText}
					<svg
						class="[ self-center ]"
						version="1.2"
						xmlns="http://www.w3.org/2000/svg"
						xmlns:xlink="http://www.w3.org/1999/xlink"
						overflow="visible"
						preserveAspectRatio="none"
						viewBox="0 0 26 26"
						width="24"
						height="24"
						fill="inherit"
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
			</div>
		</div>
	</article>
</section>

<style>
	*,
	*:before,
	*:after {
		box-sizing: inherit;
	}

	h2,
	p {
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

	.link {
		all: unset;
		cursor: pointer;
		font-weight: 700;
	}

	.link:hover {
		text-decoration: underline;
	}

	.mobile {
		display: block;
	}
	.desktop {
		display: none;
	}
	section {
		font-family: 'Open Sans', sans-serif;
		max-width: 1440px;
		margin-inline: auto;
		border-top: 1px solid var(--ashley-black);
		border-bottom: 1px solid var(--ashley-black);
		padding-inline: 1rem;
		padding-block: 2rem;
		margin-bottom: 64px;
	}

	article {
		display: flex;
		flex-direction: row-reverse;
		margin-inline: auto;
		gap: 1rem;
		justify-content: center;
	}
	.card {
		height: 60px;
		width: auto;
	}

	.eyebrow {
		font-family: 'Open Sans';
		font-style: normal;
		font-weight: 400;
		font-size: 16px;
		line-height: 16px;
		letter-spacing: 2px;
		text-transform: uppercase;
	}

	.maintext {
		font-size: 24px;
		font-style: normal;
		font-weight: 700;
	}

	sup {
		font-size: 0.55em;
	}

	.legalText {
		margin-block: 0.5rem;
		font-family: 'Open Sans';
		font-style: normal;
		font-weight: 400;
		font-size: 12px;
		line-height: 16px;
		letter-spacing: 0.32px;
		text-transform: capitalize;
		flex: 1;
	}

	.main {
		display: grid;
		gap: 0.25rem;
	}

	base-link {
		align-self: end;
	}

	@media (min-width: 768px) {
		article {
			display: flex;
			flex-direction: row;
		}
		.card {
			height: 100px;
			width: auto;
			align-self: center;
		}

		.mobile {
			display: none;
		}
		.desktop {
			display: block;
		}
	}

	@media (min-width: 1024px) {
		article {
			display: flex;
			flex-direction: row;
		}

		.wrapper {
			display: flex;
			gap: 1rem;
			align-items: center;
		}
	}

	*,
	*:before,
	*:after {
		box-sizing: inherit;
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
	}

	a:hover {
		color: var(--gray-6);
	}

	.size {
		font-size: 0.75rem;
	}
	.color {
		color: #fff;
		fill: #fff;
	}
	.color:hover {
		color: var(--gray-1);
		fill: var(--gray-1);
	}
</style>
