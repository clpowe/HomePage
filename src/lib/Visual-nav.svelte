<svelte:options tag="visual-nav" />

<script lang="ts">
	import { slide } from 'svelte/transition'

	type MenuItem = {
		image: string
		text: string
		altText: string
		ariaLabel: string
		link: string
	}

	type Section = {
		id: number
		category: string
		title: string
		anchor: string
		copy: string
		mainImage: string
		tabletImage: string
		mobileImg: string
		altText: string
		linktext: string
		ariaLabel: string
		link: string
		items: MenuItem[]
	}

	type Data = Section[]

	export let data = [] as Data

	let isExpanded: boolean = false

	function clickHandler() {
		isExpanded = !isExpanded
	}

	let activeItem: string = 'bedroom'
</script>

<snap-tabs>
	<header>
		<nav class="mobilenav">
			<button on:click={clickHandler} class:navopen={isExpanded === true}>
				<span> shop by category </span>
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
			</button>
			{#if isExpanded}
				<ul
					transition:slide
					class="dropdown [ hotspot-image hotspot-v2-container ]"
				>
					{#each data as item}
						<li><a href={item.link}>{item.title}</a></li>
					{/each}
				</ul>
			{/if}
		</nav>
		<nav class="desktopnav">
			{#each data as item}
				{#if !item.mobile}
					<button
						class:see={item.title === activeItem}
						class:line={item.title === activeItem}
						href={item.anchor}
						on:click={() => {
							activeItem = item.title
						}}>{item.category}</button
					>
				{/if}
			{/each}
		</nav>
	</header>
	<section class="big-flow">
		{#each data as item}
			{#if !item.mobile}
				<article class:active={item.title === activeItem} class="container">
					<h2 class="mainText">{item.copy}</h2>
					<div class="vnav">
						<div class="content">
							<picture>
								<source srcset={item.mainImage} media="(min-width: 1024px)" />
								<source srcset={item.mainImage} media="(min-width: 768px)" />
								<source srcset={item.tabletImage} media="(min-width: 375px)" />
								<img
									src={item.mobileImg}
									class="mainimage"
									alt={item.altText}
									loading="lazy"
								/>
							</picture>

							<div class="link-container hotspot-image hotspot-v2-container">
								<base-link
									text={item.linktext}
									href={item.link}
									aria-label={item.ariaLabel}
								/>
							</div>
						</div>
						<div class="menu hotspot-image hotspot-v2-container">
							{#each item.items as link}
								<a href={link.link} aria-label={link.ariaLabel}>
									<img
										src={link.image}
										alt=""
										rel="lazy"
										class="image transition-all"
									/>
									<p class="">
										{link.text}
									</p>
								</a>
							{/each}
						</div>
					</div>
				</article>
			{/if}
		{/each}
	</section>
</snap-tabs>

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

	.big-flow > :not(:first-child) {
		margin-top: 4rem;
	}
	.big-flow > .container:nth-child(even) {
		text-align: center;
	}

	.link-container {
		background-color: transparent;
		display: flex;
		justify-content: end;
		padding: 0.5rem;
	}

	.mobilenav {
		padding-block: 1rem;
		position: sticky;
		top: 187px;
	}

	.mobilenav button {
		width: auto;
		box-sizing: border-box;
		text-transform: lowercase;
		display: flex;
		margin-inline: auto;
		border-radius: 4px 4px 4px 4px;
		background-color: #fff;
		border: 1px solid var(--ashley-black);
		overflow: hidden;
		will-change: auto;
		align-items: center;
		width: min(100%, 400px);
		font-size: 1rem;
		padding-block: 0.5rem;
		padding-inline: 1rem;
		justify-content: space-between;
	}
	.mobilenav button span {
	}

	.mobilenav .navopen {
		background-color: var(--gray-1);
		border-bottom: none;
		border-radius: 4px 4px 0px 0px;
	}

	.mobilenav ul {
		box-sizing: border-box;
		position: absolute;
		display: block;
		width: min(100%, 400px);
		margin-inline: auto;
		background: #fff;
		padding: 0%;
		left: 50%;
		border-radius: 0px 0px 4px 4px;
		border: 1px solid var(--ashley-black);
		border-top: none;
		transform: translateX(-50%);
	}

	.mobilenav li {
		list-style: none;
		padding-block: 0.5rem;
		padding-inline: 1rem;
	}
	.mobilenav li:hover {
		background: var(--gray-1);
	}

	.mobilenav li a {
		color: #000;
		justify-content: start;
		text-decoration: none;
		letter-spacing: 3px;
	}

	.desktopnav {
		display: none;
		justify-content: center;
		margin-bottom: 2rem;
		gap: 1.5rem;
	}

	.desktopnav button {
		scroll-snap-align: start;
		display: inline-flex;
		align-items: center;
		white-space: nowrap;
		width: auto;
		text-align: center;
		justify-content: center;
	}

	.desktopnav button {
		background: none;
		border: none;
		text-transform: uppercase;
		font-size: clamp(14px, 1vw, 16px);
		letter-spacing: 0.3em;
		font-weight: 400;
		padding-block: 1rem;
		cursor: pointer;
		position: relative;
	}

	.desktopnav button::after {
	}

	.desktopnav button::after.see {
	}

	snap-tabs {
		max-width: 1440px;
		margin-inline: auto;
		display: flex;
		flex-direction: column;
		font-family: 'Open Sans', sans-serif;
		position: relative;
		margin-bottom: 6rem;
	}

	.mainText {
		font-family: 'Open Sans', sans-serif;
		text-transform: lowercase;
		font-weight: 700;
		font-size: clamp(28px, 4vw, 36px);
		line-height: 2.25rem;
		margin-bottom: 1rem;
	}

	snap-tabs > section {
		block-size: 100%;
	}

	a {
		display: flex;
		align-items: center;
		justify-content: flex-start;
		text-transform: uppercase;
		letter-spacing: 1.2px;
		background-color: transparent;
		justify-content: flex-end;
		padding: 0.5rem;
	}

	a > p {
		margin-top: auto;
		font-size: 0.875rem;
	}

	snap-tabs > header {
		flex-shrink: 0;
		min-block-size: fit-content;
		position: sticky;
		top: 113px;
		background: #fff;
	}

	section {
		block-size: 100%;
		display: grid;
		grid-auto-flow: row;
		grid-auto-columns: 100%;
		padding-inline: 1rem;
	}

	.container {
		display: block;
		width: 100%;
		margin-right: auto;
		margin-left: auto;
	}

	.vnav {
		display: grid;

		gap: 1rem;
	}

	.mainimage {
		width: 100%;
		object-fit: cover;
		height: auto;
	}

	.content {
		display: flex;
		flex-direction: column;
		gap: 1rem;
	}

	h2 {
		font-size: 28px;
		font-weight: 600;
		text-transform: lowercase;
	}

	base-link {
		align-self: end;
	}

	.menu {
		display: none;
		grid-template-columns: 1fr 1fr;
		gap: 1rem;
	}

	.menu > a {
		display: flex;
		text-align: center;
		flex-direction: column;
		justify-content: center;
		padding: 0.5rem;
		cursor: pointer;
		align-items: center;
		text-decoration: none;
	}
	a > p {
		font-size: 14px;
	}
	a > p:hover {
		color: var(--gray-6);
		font-size: 14px;
	}

	a > img {
		filter: drop-shadow(0 1px 1px rgba(136, 136, 136, 0.4))
			drop-shadow(0 2px 2px rgba(136, 136, 136, 0.4));
		will-change: auto;
		transition: all 0.5s ease-in-out;
		max-height: 100px;
		margin-top: auto;
	}
	a > img:hover {
		transform: translateY(-4px) scale(1.05);
		filter: drop-shadow(0 6px 6px rgba(136, 136, 136, 0.5))
			drop-shadow(0 2px 2px rgba(136, 136, 136, 0.3));
	}

	@media (min-width: 479px) {
		snap-tabs > header {
			top: 163px;
		}
	}
	@media (min-width: 679px) {
		.mainimage {
			height: 40rem;
		}
	}

	@media (min-width: 768px) {
		snap-tabs > header {
			top: 143px;
		}
	}

	@media (min-width: 1024px) {
		snap-tabs > header {
			position: relative;
			top: 0;
			background: #fff;
		}

		.link-container {
			background-color: var(--gray-1);
		}

		.vnav {
			display: grid;
			grid-template-columns: auto 400px;
		}
		.menu {
			display: grid;
		}

		section {
			block-size: 100%;

			display: grid;
			grid-auto-flow: column;
			grid-auto-columns: 100%;
		}

		.container {
			display: none;
			width: 100%;
			margin-right: auto;
			margin-left: auto;
		}

		a {
			background-color: var(--gray-1);
			color: var(--ashley-black);
		}

		.big-flow > :not(:first-child) {
			margin-top: 0;
		}
		.big-flow > .container:nth-child(even) {
			text-align: left;
		}

		.mobilenav {
			display: none;
		}
		.desktopnav {
			display: flex;
		}
	}

	@media (min-width: 1280px) {
		.container {
			max-width: 1440px;
		}
	}

	.active {
		display: block;
	}

	.see::after {
	}

	.see {
		text-decoration: underline;
		text-underline-offset: 0.5rem;
		text-decoration-thickness: 0.1rem;
	}

	.see:after {
		opacity: 1;
		transform: translateX(0%);
	}
</style>
