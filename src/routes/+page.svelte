<script lang="ts">
	// goto lets us navigate client-side, the same way clicking a normal
	// <a href> link would, but from inside a click handler.
	import { goto } from '$app/navigation';
	// our reusable button component - see src/lib/components/Button.svelte.
	// demo: this is the same component used below for "sign in with discord".
	import Button from '$lib/components/Button.svelte';

	const tabs = ['All', 'Events', 'Workshops'];
	let active = $state('All');

	const events = ['Event 1', 'Event 2', 'Event 3'];
</script>

<!-- nav bar -->
<header class="border-b border-neutral-200 bg-white">
	<div class="mx-auto flex max-w-xl items-center justify-between px-6 py-4">
		<span class="font-semibold">dash</span>

		<nav class="flex gap-6 text-sm">
			{#each tabs as tab}
				<button
					class="border-b-2 pb-1 {active === tab
						? 'border-neutral-900'
						: 'border-transparent text-neutral-500 hover:text-neutral-900'}"
					onclick={() => (active = tab)}
				>
					{tab}
				</button>
			{/each}
		</nav>
	</div>
</header>

<main class="mx-auto flex max-w-xl flex-col gap-8 p-6 text-center">
	<!-- demo: this heading's color and font both come from global.css's
	     body styles - nothing here sets them directly. -->
	<h1 class="text-2xl">Welcome to dash.acmcsuf.com</h1>

	<!-- demo: <Button> replaces what used to be a plain <a> link.
	     onclick calls goto() to still navigate to /auth/discord, but now
	     we get our shared color/hover-animation styling for free.
	     hover it live to show the sideways bounce + outline animation,
	     and point out that its blue color is global.css's --color-primary. -->
	<p>
		<Button onclick={() => goto('/auth/discord')}>Sign in with Discord</Button>
	</p>

	<h2>Upcoming {active}</h2>

	{#each events as event}
		<div class="rounded-full border px-5 py-3">{event}</div>
	{/each}
</main>