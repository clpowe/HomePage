<svelte:options tag="corporate-two" />

<script lang="ts">
	type item = {
		id: number
		icon: string
		title: string
		text: string
		link: string
		ariaLabel: string
	}

	export let data: item[] = [
		{
			id: 1,
			icon: 'images/homepage/20220712/ICON_PriceMatchGuarantee.svg?$staticlink$',
			title: 'price match guarantee',
			text: '',
			link: '/price-match/',
			ariaLabel: 'price match guarantee'
		},
		{
			id: 2,
			icon: 'images/homepage/20220712/ICON_ReferAFriend.svg?$staticlink$',
			title: 'refer a friend',
			text: '',
			link: '/referafriend/',
			ariaLabel: 'refer a friend'
		},
		{
			id: 3,
			icon: 'images/homepage/20220712/ICON_ThisIsHomeYourWay.svg?$staticlink$',
			title: 'this is home your way',
			text: '',
			link: '/this-is-home-your-way/',
			ariaLabel: 'this is home your way'
		},
		{
			id: 4,
			icon: 'images/homepage/20220712/ICON_OrangeRewards.svg?$staticlink$',
			title: 'Orange Rewards',
			text: '',
			link: '/orange-rewards/',
			ariaLabel: 'Orange Rewards'
		}
	]
</script>

<section id="homepage-main">
	<div class="home-content corporate-two">
		{#each data as item}
			<div
				class="
              corporate-two__item
              text-center
              [
              hotspot-image hotspot-v2-container
              ]
            "
			>
				<img src={item.icon} alt="" loading="lazy" />
				<h3 class="[ text-lowercase m-0 ]">{item.title}</h3>
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
		margin-inline: auto;
	}

	a:hover {
		color: var(--gray-6);
	}

	.corporate-two {
		font-family: 'Open Sans', sans-serif;
		max-width: 1440px;
		margin-inline: auto;
		display: grid;
		margin-block: var(--size-fluid-7);
		background-color: var(--gray-1);
		margin-bottom: 6rem;
	}

	.corporate-two__item {
		text-align: center;
		display: flex;
		flex-direction: column;
		padding-bottom: 3rem;
		margin-top: 3rem;
		margin-inline: 1rem;
		justify-content: space-between;
		gap: 1rem;
	}
	.corporate-two__item > h3 {
		font-weight: 700;
		padding: 0;
	}
	.corporate-two div:not(:last-child) {
		border-right: none;
		border-bottom: 1px solid var(--ashley-black);
	}

	.corporate-two__item p {
		max-width: 35ch;
	}

	.corporate-two__item > img {
		width: 72px;
		margin-inline: auto;
	}

	@media (min-width: 768px) {
		.corporate-two {
			display: grid;
			grid-template-columns: repeat(4, 1fr);
			padding: 2rem;
			gap: 1rem;
		}
		.corporate-two__item {
			text-align: center;
			display: flex;
			flex-direction: column;
			padding-bottom: 0;
			margin-top: 0;
			margin-inline: 0;
			padding: 2rem;
			justify-content: space-between;
		}
		.corporate-two div:not(:last-child) {
			border-right: 1px solid var(--ashley-black);
			border-bottom: none;
		}
	}
</style>
