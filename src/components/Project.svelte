<script lang="ts">
	export let name: string;
	export let url: string;
	export let src: string;
	export let description: string;
</script>

<li>
	<a href={url} aria-labelledby="new-window-external-self">
		<picture>
			<source srcset={`/img/${src}.avif`} type="image/avif" />
			<img src={`/img/${src}.png`} alt={description} />
		</picture>
		<h3>{name}</h3>
	</a>
</li>

<style>
	a {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		gap: 1rem;
		height: 100%;
		width: 100%;
		max-width: 18rem;
		text-decoration: none;
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
		transition: transform 0.3s ease-in-out, border-color 0.3s ease-in-out;
		max-width: 325px;
		max-height: 325px;
		min-height: 200px;
		min-width: 200px;
	}

	a:hover img {
		border-color: var(--primary-700);
		transform: rotate(5deg);
		will-change: transform, border-color;
	}

	h3 {
		color: var(--text-primary);
		font-size: 1.2rem;
		font-weight: 700;
	}
</style>
