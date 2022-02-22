<script lang="ts">
	export let name: string;
	export let url: string;
	export let src: string;
	export let description: string;
</script>

<a href={url}>
	<img {src} alt={description} />
	<h3>{name}</h3>
</a>

<style>
	a {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		gap: 1rem;
		height: 100%;
		width: 100%;
		max-width: 22rem;
	}

	a:hover {
		cursor: pointer;
	}

	img {
		width: 100%;
		border: 6px solid var(--gray-500);
		object-fit: cover;
		border-radius: 8px;
		aspect-ratio: 1/1;
		transition: transform 0.3s ease-in-out;
		min-height: 352px;
		min-width: 352px;
	}

	a:hover img {
		border-color: var(--primary-700);
		transform: rotate(5deg);
	}

	h3 {
		color: var(--text-primary);
		font-size: 1.2rem;
		font-weight: 700;
	}
</style>
