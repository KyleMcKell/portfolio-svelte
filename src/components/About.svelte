<script>
	import ExternalLink from './ExternalLink.svelte';
</script>

<section>
	<article>
		<p>
			I&apos;m a self-taught front-end developer
			<span class="snazzy"> ADHD-</span>ing my way through the world of web
			development
		</p>
		<p>
			I have a passion for teaching others, and if you're interested, you can
			follow along on my
			<ExternalLink href="https://twitter.com/KyleMcKell">Twitter</ExternalLink>
		</p>
		<p>
			While you're at it, you can check out my
			<ExternalLink href="https://github.com/KyleMcKell">GitHub</ExternalLink>
		</p>
		<p>
			My current tech stack includes
			<span class="tech" href="https://reactjs.org/"> React</span>,
			<span class="tech" href="https://www.typescriptlang.org/">
				TypeScript</span
			>, and a UI framework. Currently my favorites are
			<span class="tech" href="https://nextjs.org/"> Next.js</span>,
			<span class="tech" href="https://remix.run/"> Remix</span>, and
			<span class="tech" href="https://kit.svelte.dev/"> SvelteKit</span>
		</p>
		<p>
			I also LOVE writing <span class="snazzy pink"> NIFTY </span>CSS!
		</p>
		<p>☕ Let's chat sometime 💙</p>
	</article>

	<picture>
		<source type="image/avif" srcset="/img/me.avif" />
		<img src="/img/me.png" alt="Kyle McKell holding a plant" />
	</picture>
</section>

<style>
	section {
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
		gap: 4rem;
		background-color: var(--bg-secondary);
		width: 100%;
		padding: 4rem 3rem;
	}

	article {
		max-width: 450px;
		font-weight: 450;
		line-height: 1.7;
		font-size: 1.2rem;
		display: flex;
		height: 100%;
		justify-content: space-around;
		flex-direction: column;
		gap: 1rem;
	}

	img {
		width: 20rem;
		min-width: 10rem;
		aspect-ratio: 1/1;
		border-radius: 50%;
		border: 5px solid var(--gray-500);
		transition: transform 0.3s ease-in-out, border-color 0.3s ease-in-out;
	}

	img:hover {
		border-color: var(--primary-700);
		transform: rotate(5deg);
		will-change: transform, border-color;
	}

	.tech {
		color: var(--primary-300);
	}

	.snazzy {
		font-family: var(--font-snazzy);
	}

	.snazzy.pink {
		color: var(--secondary-300);
	}

	@media (max-width: 1000px) {
		section {
			flex-direction: column-reverse;
			width: 100%;
		}
	}
</style>
