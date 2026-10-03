<<<<<<< HEAD
<script lang="ts">
	import type { Snippet } from 'svelte';

	type Props = {
		color?: string;
		disabled?: boolean;
		onclick?: () => void;
		children: Snippet;
	};

	let { color = 'var(--color-primary)', disabled = false, onclick, children }: Props = $props();
</script>

<button class="btn" style:--btn-color={color} {disabled} {onclick}>
	{@render children()}
</button>

<style>
	.btn {
		font-family: var(--font-family-base);
		font-size: 1rem;
		font-weight: 600;
		padding: 0.6rem 1.4rem;
		border: none;
		border-radius: var(--radius-base);
		cursor: pointer;
		color: white;
		background-color: var(--btn-color);

		outline: 2px solid transparent;
		outline-offset: 2px;

		transition:
			outline-color 0.2s ease,
			outline-offset 0.2s ease;
	}

	.btn:hover:not(:disabled) {
		outline-color: var(--btn-color);
		outline-offset: 5px;
		animation: bounce-sideways 0.4s ease-in-out;
	}

	@keyframes bounce-sideways {
		0%,
		100% {
			transform: translateX(0);
		}
		25% {
			transform: translateX(-6px);
		}
		75% {
			transform: translateX(6px);
		}
	}

	.btn:disabled {
		opacity: 0.5;
		cursor: not-allowed;
	}
</style>
=======
 
<script lang="ts">
    import type { Snippet } from 'svelte';

    type Props = {
        color?: string;
        disabled?: boolean;
        onclick?: () => void;
        children: Snippet;
    };

    let { color = 'var(--color-primary)', disabled = false, onclick, children }: Props = $props();
</script>

<button class="btn" style:--btn-color={color} {disabled} {onclick}>
    {@render children()}
</button>

<style>
    .btn {
        font-family: var(--font-family-base);
        font-size: 1rem;
        font-weight: 600;
        padding: 0.6rem 1.4rem;
        border: none;
        border-radius: var(--radius-base);
        cursor: pointer;
        color: white;
        background-color: var(--btn-color);

        outline: 2px solid transparent;
        outline-offset: 2px;

        transition:
            outline-color 0.2s ease,
            outline-offset 0.2s ease;
    }

    .btn:hover:not(:disabled) {
        outline-color: var(--btn-color);
        outline-offset: 5px;
        animation: bounce-sideways 0.4s ease-in-out;
    }

    @keyframes bounce-sideways {
        0%,
        100% {
            transform: translateX(0);
        }
        25% {
            transform: translateX(-6px);
        }
        75% {
            transform: translateX(6px);
        }
    }

    .btn:disabled {
        opacity: 0.5;
        cursor: not-allowed;
    }
</style>
>>>>>>> d3efd61 (Test)
