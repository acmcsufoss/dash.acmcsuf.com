<script lang="ts">
	import './layout.css'; // tailwind utility classes (used by the homepage)
	import '$lib/styles/global.css'; // our base global styles (fonts, colors, resets)
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();
</script>

<svelte:head><link rel="icon" href={favicon} /></svelte:head>
{@render children()}
