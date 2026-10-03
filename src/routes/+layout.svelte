<script lang="ts">
<<<<<<< HEAD
	import './layout.css';
	import '$lib/styles/global.css';
	import favicon from '$lib/assets/favicon.svg';
=======
    import './layout.css';
    import '$lib/styles/global.css';
    import favicon from '$lib/assets/favicon.svg';
>>>>>>> d3efd61 (Test)

    let { children } = $props();
</script>

<svelte:head><link rel="icon" href={favicon} /></svelte:head>
{@render children()}