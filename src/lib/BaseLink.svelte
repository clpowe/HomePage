<svelte:options tag="base-link" />

<script lang="ts">
	export let href: string
	export let text: string
	export let ariaLabel: string

	export let light: boolean
	export let small: boolean
	export let finance: boolean
</script>

<!-- svelte-ignore a11y-missing-attribute -->
<a
	aria-label={ariaLabel}
	class:color={light}
	class:size={small}
	class:finance-dk2-pq={finance}
	{href}
	>{text}
	<svg
		class="[ self-center ]"
		class:color={light}
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

<style>
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
