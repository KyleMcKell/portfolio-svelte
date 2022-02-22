<section>
	<article>
		<p>
			I&apos;m a self-taught front-end developer
			<span> ADHD-</span>ing my way through the world of web development
		</p>
		<p>
			I have a passion for teaching others, and if you're interested, you can
			follow along on my
			<a href="https://twitter.com/KyleMcKell"> Twitter</a>
		</p>
		<p>
			While you're at it, you can check out my
			<a href="https://github.com/KyleMcKell"> GitHub</a>
		</p>
		<p>
			My current tech stack includes
			<a href="https://reactjs.org/"> React</a>,
			<a href="https://www.typescriptlang.org/"> TypeScript</a>, and a UI
			framework. Currently my favorites are
			<a href="https://nextjs.org/"> Next.js</a>,
			<a href="https://remix.run/"> Remix</a>, and
			<a href="https://kit.svelte.dev/"> SvelteKit</a>
		</p>
		<p>
			I also LOVE writing <span class="pink"> NIFTY </span>CSS!
		</p>
		<p>☕ Let's chat sometime 💙</p>
	</article>

	<a tabindex="-1" href="https://twitter.com/KyleMcKell">
		<picture>
			<source type="image/avif" srcset="/img/me.avif" />
			<img src="/img/me.png" alt="Kyle McKell holding a plant" />
		</picture>
	</a>
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
		cursor: pointer;
	}

	a {
		color: var(--primary-300);
		text-decoration: none;
	}

	a:hover {
		cursor: pointer;
		color: var(--primary-500);
		text-decoration: underline;
	}

	span {
		font-family: var(--font-snazzy);
	}

	span.pink {
		color: var(--secondary-300);
	}

	@media (max-width: 1000px) {
		section {
			flex-direction: column-reverse;
			width: 100%;
		}
	}
</style>
