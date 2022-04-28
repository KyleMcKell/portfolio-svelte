<script lang="ts">
	export let name: string;
	export let url: string;
	export let src: string;
	export let description: string;
</script>

<li>
	<h3>{name}</h3>
	<article>
		<div>
			<p>{description}</p>
			<a href={url} on:mouseenter={() => {}}>
				<button>Live site</button>
			</a>
		</div>

		<a href={url}>
			<picture>
				<source srcset={`/img/${src}.avif`} type="image/avif" />
				<img src={`/img/${src}.png`} alt={description} />
			</picture>
		</a>
	</article>
</li>

<style>
	li {
		display: flex;
		flex-direction: column;
		width: 100%;
		gap: 1rem;
		max-width: 800px;
	}

	h3 {
		margin-left: 2rem;
		font-size: 1.625rem;
	}

	p {
		font-weight: 400;
		font-size: 1.125rem;
	}

	a {
		text-decoration: none;
		color: inherit;
	}

	article {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		position: relative;
		padding: 2rem;
		min-height: 15rem;
		width: 100%;
		background-color: var(--gray-700);
		border-radius: 8px;
	}

	div {
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: flex-start;
		width: 30%;
	}

	picture {
		position: absolute;
		right: 2rem; /* match padding of article */
		top: -30px;
		margin: auto;
	}

	picture img {
		width: 100%;
		border: 6px solid var(--gray-500);
		object-fit: cover;
		border-radius: 8px;
		aspect-ratio: 1/1;
		transition: transform 0.3s ease-in-out, border-color 0.3s ease-in-out;
		max-width: 300px;
		max-height: 300px;
		min-height: 200px;
		min-width: 200px;
	}

	img:hover {
		border-color: var(--primary-700);
		transform: rotate(5deg);
		will-change: transform, border-color;
	}

	button {
		border: none;
		padding: 0.5rem 1rem;
		min-width: 8rem;
		border-radius: 4px;
		font-family: inherit;
		font-size: 1rem;
		font-weight: 500;
		color: var(--gray-800);
		background-color: var(--primary-800);
		transition: background-color 0.5s ease;
	}

	button:hover {
		cursor: pointer;
		box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1);
		background-color: var(--primary-600);
	}

	@media (max-width: 800px) {
		picture {
			position: revert;
			right: 0;
		}
		img {
			max-height: 200px;
			max-width: 200px;
		}
	}
</style>
