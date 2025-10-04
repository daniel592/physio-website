<script lang="ts">
	import '../app.css';
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
	<title>Holistic Physiotherapy - Healing Mind, Body & Spirit</title>
</svelte:head>

{@render children?.()}
