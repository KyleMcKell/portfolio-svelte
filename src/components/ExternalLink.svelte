<script lang="ts">
	export let href: string;
	export let target: string = '_self';

	$: ariaDescribedBy =
		target === '_self' ? 'link-external-self' : 'link-external-blank';
</script>

<a {href} {target} aria-describedby={ariaDescribedBy}>
	<slot />
</a>

<style>
	a {
		color: var(--primary-300);
		transition: color 0.25s linear;
	}

	a::after {
		background-color: currentColor;
		display: inline-block;
		content: '';
		height: 16px;
		width: 16px;
		margin-left: 3px;
		mask: url(/img/external-link.svg);
		mask-size: cover;
		-webkit-mask: url(/img/external-link.svg);
		-webkit-mask-size: cover;
	}

	a:hover {
		cursor: pointer;
		text-decoration: none;
		color: var(--primary-500);
	}
</style>
