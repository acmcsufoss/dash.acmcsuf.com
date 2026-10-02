<script lang="ts">
<<<<<<< HEAD
	import { goto } from '$app/navigation';
	import Button from '$lib/components/Button.svelte';

	const tabs = ['All', 'Events', 'Workshops'];
	let active = $state('All');
=======
    import { goto } from '$app/navigation';
    import Button from '$lib/components/Button.svelte';
>>>>>>> d3efd61 (Test)

    const tabs = ['All', 'Events', 'Workshops'];
    let active = $state('All');

    const events = ['Event 1', 'Event 2', 'Event 3'];
</script>

<!-- nav bar -->
<header class="border-b border-neutral-200 bg-white text-neutral-900">
<<<<<<< HEAD
	<div class="mx-auto flex max-w-xl items-center justify-between px-6 py-4">
		<span class="font-semibold">dash</span>
=======
    <div class="mx-auto flex max-w-xl items-center justify-between px-6 py-4">
        <span class="font-semibold">dash</span>
>>>>>>> d3efd61 (Test)

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

<<<<<<< HEAD
	<p>
		<Button onclick={() => goto('/auth/discord')}>Sign in with Discord</Button>
	</p>
=======
    <p>
        <Button onclick={() => goto('/auth/discord')}>Sign in with Discord</Button>
    </p>
>>>>>>> d3efd61 (Test)

    <h2>Upcoming {active}</h2>

    {#each events as event}
        <div class="rounded-full border px-5 py-3">{event}</div>
    {/each}
</main>
