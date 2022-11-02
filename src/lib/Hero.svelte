<svelte:options tag="home-hero" />

<script lang="ts">
	type Hero = {
		pretext: string
		maintext: string
		items: string
		subtext: string
		code: string
		img: string
		imgXLDesktop: string
		imgDesktop: string
		imgTablet: string
		ariaLabel: string
		link: string
	}

	export let data = {} as Hero
</script>

<section class="Hero container w-full relative ">
	<article class="hero-container ">
		<div class="content ">
			<div class="holder ">
				<div class="[ hotspot-image hotspot-v2-container ]">
					<div class="words text-center sm:(text-left) mb-4">
						<p class="pretext uppercase font-light tracking-wider">
							{data.pretext}
						</p>
						<h2 class="maintext">
							{data.maintext} <sup>{data.items}</sup>
						</h2>
						<p class="subtext">{data.subtext}</p>
						<p>{data.code}</p>
					</div>
					<a
						href={data.link}
						aria-label={data.ariaLabel}
						class="btn mx-auto sm:(mx-0)"
					>
						shop now
					</a>
				</div>
			</div>
		</div>
	</article>
	<picture>
		<source srcset={data.imgXLDesktop} media="(min-width: 1440px)" />
		<source srcset={data.imgDesktop} media="(min-width: 768px)" />
		<source srcset={data.imgTablet} media="(min-width: 486px)" />
		<img
			class="w-full block min-h-[340px] object-cover "
			src={data.img}
			loading="eager"
			alt=""
		/>
	</picture>
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

	a:hover {
		text-decoration: underline;
	}

	.Hero {
		font-family: 'Open Sans', sans-serif;
		width: 100%;
		position: relative;
		overflow: hidden;
		max-height: 693px;
		background: var(--gray-1);
	}

	img {
		width: 100%;
		display: block;
		min-height: 340px;
		object-fit: cover;
	}

	.content {
		font-family: 'Open Sans', sans-serif;
		position: relative;
		display: flex;
		flex-direction: row;
		height: 100%;
		gap: 1rem;
		margin-inline: auto;
		max-width: 1280px;
	}

	.holder {
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: center;
		width: 100%;
		height: 100%;
		gap: 1rem;
		padding: 1rem;
		background: var(--gray-1);
	}

	.holder > div {
		display: flex;
		flex-direction: column;
		width: 100%;
	}

	.words {
		font-family: 'Open Sans', sans-serif;
		text-align: center;
		margin-bottom: 1em;
	}

	sup {
		font-size: 0.55em;
	}

	.container {
		width: 100%;
		margin-right: auto;
		margin-left: auto;
	}

	.hero-container {
		max-width: 1440px;
		width: 100%;
		margin-right: auto;
		margin-left: auto;
	}
	.pretext {
		text-transform: uppercase;
		font-weight: 300;
		letter-spacing: 0.05em;
		font-size: clamp(13px, 1px + 2vw, 20px);
		margin-bottom: 0.25em;
	}

	.maintext {
		font-family: 'Open Sans', sans-serif;
		text-transform: lowercase;
		font-weight: 700;
		font-size: clamp(28px, 4vw, 36px);
		line-height: 2.25rem;
		margin-bottom: 0.25em;
	}

	.subtext {
		font-size: clamp(13px, 1px + 2vw, 22px);
	}

	.btn {
		margin-inline: auto;
		font-family: 'Open Sans', sans-serif;
		font-weight: 700;
		background: var(--ashley-black);
		color: #fff;
		padding-inline: 1rem;
		padding-block: 0.5rem;
		border-radius: 0.25rem;
	}
	.btn > button {
	}
	.btn:hover {
		background: #525252;
		text-decoration: none;
	}

	@media (min-width: 640px) {
		.holder > div {
			display: flex;
			flex-direction: row;
			align-items: end;
			justify-content: space-around;
		}

		.words {
			text-align: left;
			margin-bottom: 1rem;
		}

		.btn {
			margin-inline: 0;
		}
	}

	@media (min-width: 768px) {
		.content {
			position: absolute;
			margin-left: 3.5rem;
			max-width: 22rem;
		}

		.holder {
			width: 25rem;
		}
		.holder > div {
			display: flex;
			flex-direction: column;
			align-items: start;
			width: auto;
		}
	}

	@media (min-width: 1024px) {
	}

	@media (min-width: 1280px) {
		.container {
			max-width: 160em;
		}
	}
</style>
