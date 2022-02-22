<header>
	<h1 class="name">Kyle McKell</h1>
	<!-- <h2>Hello! I'm</h2> -->
</header>

<style>
	header {
		padding: 4rem 3rem;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		position: relative;
	}

	h1 {
		font-size: 4rem;
		font-weight: 700;
		color: var(--text-secondary);
		position: relative;
	}

	h1::before {
		content: "Hello! I'm";
		position: absolute;
		font-family: var(--font-snazzy);
		font-size: 1.5rem;
		top: -24px;
		left: -32px;
		transform: rotate(-7deg);
		color: var(--secondary-300);
		font-weight: 400;
	}
</style>
