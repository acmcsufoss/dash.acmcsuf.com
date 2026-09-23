<script lang="ts">
	// this component is a reusable button. instead of writing
	// <button class="..."> everywhere with copy-pasted styles, we write
	// <Button> once and reuse it across the whole app.
	//
	// demo: open the homepage ("/") - the "sign in with discord" button
	// is this exact component in action.

	// import svelte's built-in "snippet" type so typescript understands
	// that `children` is renderable content (the stuff between
	// <Button> ...here... </Button>).
	import type { Snippet } from 'svelte';

	// this describes every prop button.svelte can receive from a parent.
	type Props = {
		color?: string; // any css color - hex, a color name, or var(--something)
		disabled?: boolean; // disables clicking + greys out the button
		onclick?: () => void; // function to run when the button is clicked
		children: Snippet; // the label/content inside the button
	};

	// $props() is how svelte 5 reads the props passed into this component.
	// we destructure them and set default values using "=".
	// the default color falls back to global.css's --color-primary (#05a3ff),
	// so a <Button> with no color prop at all still looks on-brand.
	let { color = 'var(--color-primary)', disabled = false, onclick, children }: Props = $props();
</script>

<!--
  we render a real <button> element (good for accessibility/keyboard use).
  style:--btn-color sets a css custom property scoped to this one button,
  which the <style> block below reads. this is how "color customization"
  works: no variant classes to maintain, just pass any color as a prop.
-->
<button class="btn" style:--btn-color={color} {disabled} {onclick}>
	<!-- {@render children()} outputs whatever was placed between the
	     opening and closing <Button> tags, e.g. "Sign in with Discord" -->
	{@render children()}
</button>

<style>
	.btn {
		font-family: var(--font-family-base); /* reuse the global font */
		font-size: 1rem;
		font-weight: 600;
		padding: 0.6rem 1.4rem;
		border: none;
		border-radius: var(--radius-base); /* reuse the global corner radius */
		cursor: pointer; /* shows a "clickable" hand icon on hover */
		color: white;
		background-color: var(--btn-color); /* comes from the color prop above */

		/* an invisible outline that we'll grow and color in on hover -
		   starting it transparent means it takes no visual space until
		   the hover state below turns it on */
		outline: 2px solid transparent;
		outline-offset: 2px;

		transition:
			outline-color 0.2s ease,
			outline-offset 0.2s ease;
	}

	/* demo: this is "the cool hover effect" - hover the sign-in button
	   on the homepage to see it wiggle side to side and grow a glowing
	   outline in its own color. */
	.btn:hover:not(:disabled) {
		outline-color: var(--btn-color);
		outline-offset: 5px;
		animation: bounce-sideways 0.4s ease-in-out;
	}

	/* the sideways bounce: nudge left, then right, then settle back */
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

	/* disabled buttons look faded and show a "not-allowed" cursor */
	.btn:disabled {
		opacity: 0.5;
		cursor: not-allowed;
	}
</style>
