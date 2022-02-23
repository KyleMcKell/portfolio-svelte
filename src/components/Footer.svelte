<script>
	import Contact from './Contact.svelte';
</script>

<footer>
	<Contact />
	<p>© Copyright Kyle McKell 2022</p>
</footer>

<style>
	footer {
		background-color: var(--bg-secondary);
		padding: 4rem 3rem 2rem;
		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
		gap: 4rem;
	}
</style>
