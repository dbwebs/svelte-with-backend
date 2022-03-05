<!-- PageTransition.svelte -->
<script>
	import { fly, scale } from 'svelte/transition';
	export let url = '';
	const pageTransitionDuration = 500;
</script>

{#key url}
	<main in:fly={{ duration: pageTransitionDuration, delay: pageTransitionDuration }} out:fly>
		<slot />
	</main>
{/key}