<script lang="ts">
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
	<h1 class="text-2xl">Welcome to dash.acmcsuf.com</h1>

	<p>
		<a href="/auth/discord" class="rounded-full border px-6 py-3">Sign in with Discord</a>
	</p>

	<h2>Upcoming {active}</h2>

	{#each events as event}
		<div class="rounded-full border px-5 py-3">{event}</div>
	{/each}
</main>