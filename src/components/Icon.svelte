<script lang="ts">
	import { CoffeeIcon, ExternalLinkIcon } from 'svelte-feather-icons';

	type IconIDs = 'coffee' | 'externalLink';

	export let id: IconIDs;
	export let color: string = 'currentColor';
	export let size: string = '24';
	export let strokeWidth: string = '2';
	export let fill: string = 'none';

	const icons: { [key in IconIDs]: any } = {
		coffee: CoffeeIcon,
		externalLink: ExternalLinkIcon,
	};

	$: icon = icons[id];
	$: if (icon) {
		if (size) icon.size = size;
		if (strokeWidth) icon.strokeWidth = strokeWidth;
		if (fill) icon.fill = fill;
	} else {
		throw new Error(`No icon found for ID: ${id}`);
	}
	$: Component = icon;
</script>

<div style={`color: ${color}`} {...$$restProps}>
	<Component {size} {strokeWidth} {fill} />
</div>

<style>
	div {
		display: inline-block;
	}
</style>
