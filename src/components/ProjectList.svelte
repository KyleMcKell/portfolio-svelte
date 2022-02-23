<script lang="ts">
	import Project from './Project.svelte';

	type Project = {
		name: string;
		url: string;
		description: string;
		src: string;
	};

	const projects: Project[] = [
		{
			name: 'Aeropress Tracker',
			url: 'https://aeropresstracker.com/',
			description: 'An app to track aeropress brews to make the perfect one!',
			src: 'aeropresstracker',
		},
		{
			name: 'Splitter',
			url: 'https://kylemckell.github.io/Tip-calculator/',
			description: 'Tip splitting app that uses vanilla HTML, CSS, and JS',
			src: 'splitter',
		},
		{
			name: 'Pokedex',
			url: 'https://kylemckell.github.io/Pokedex/',
			description: 'Pokedex app made with React and PokeAPI',
			src: 'pokedex',
		},
	];
</script>

<section>
	<h2>My Projects</h2>
	<ul>
		{#each projects as project (project.name)}
			<Project {...project} />
		{/each}
	</ul>
</section>

<style>
	section {
		padding: 4rem 3rem;
		display: flex;
		flex-direction: column;
		gap: 2.5rem;
	}

	h2 {
		color: var(--text-secondary);
		text-align: center;
		font-size: 2rem;
	}

	ul {
		padding: 0;
		width: fit-content;
		height: 100%;
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: space-around;
		column-gap: clamp(24px, 8px + 4vw, 72px);
		row-gap: 3rem;
		flex-wrap: wrap;
		list-style: none;
	}
</style>
