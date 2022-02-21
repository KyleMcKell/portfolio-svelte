<script>
	import Header from '../components/Header.svelte';
	import Main from '../components/Main.svelte';
	import Footer from '../components/Footer.svelte';
	import { SvelteToast } from '@zerodevx/svelte-toast';
</script>

<SvelteToast />
<Header />
<Main />
<Footer />

<style>
	:global(*) {
		box-sizing: border-box;
		margin: 0;
	}

	:global(html, body, body > div) {
		height: 100%;
	}

	:global(:root) {
		--white: hsl(216 70% 99%);
		--black: hsl(210 25% 12%);
		--gray-50: hsl(216 33% 97%);
		--gray-100: hsl(214 15% 91%);
		--gray-200: hsl(210 16% 82%);
		--gray-300: hsl(211 13% 65%);
		--gray-400: hsl(211 10% 53%);
		--gray-500: hsl(211 12% 43%);
		--gray-600: hsl(209 14% 37%);
		--gray-700: hsl(209 20% 25%);
		--gray-900: hsl(210 24% 16%);
		--primary-50: hsl(195 100% 95%);
		--primary-100: hsl(195 100% 85%);
		--primary-200: hsl(197 96% 78%);
		--primary-300: hsl(196 94% 67%);
		--primary-400: hsl(197 92% 61%);
		--primary-500: hsl(199 84% 55%);
		--primary-600: hsl(201 79% 46%);
		--primary-700: hsl(202 83% 41%);
		--primary-800: hsl(203 87% 34%);
		--primary-900: hsl(204 96% 27%);
		--secondary-50: hsl(341 100% 95%);
		--secondary-100: hsl(338 100% 86%);
		--secondary-200: hsl(336 100% 77%);
		--secondary-300: hsl(334 86% 67%);
		--secondary-400: hsl(330 79% 56%);
		--secondary-500: hsl(328 85% 46%);
		--secondary-600: hsl(326 90% 39%);
		--secondary-700: hsl(324 93% 33%);
		--secondary-800: hsl(322 93% 27%);
		--secondary-900: hsl(320 100% 19%);

		--font-snazzy: 'Sriracha', cursive;
		--font-base: 'Rubik', sans-serif;

		--text-primary: var(--white);
		--text-secondary: var(--gray-100);
		--bg-primary: var(--black);
		--bg-secondary: var(--gray-900);
	}

	:global(body) {
		background-color: var(--bg-primary);
		color: var(--text-primary);
		font-family: var(--font-base);
	}
</style>
