<script lang="ts">
	import logo from '$lib/assets/logo.png';
	import favicon from '$lib/assets/favicon.svg';
	import StarterPane from './StarterPane.svelte';
	import WhoIAm from './WhoIAm.svelte';
	import WhatITreat from './WhatITreat.svelte';
	import MyApproach from './MyApproach.svelte';
	import Services from './Services.svelte';
</script>



<svelte:head>
	<link rel="icon" href={favicon} />
	<title>Holistic Physiotherapy - Healing Mind, Body & Spirit</title>
</svelte:head>

<div class="bg-white text-gray-800 antialiased">
    <StarterPane />
    <WhoIAm />
    <WhatITreat />
    <MyApproach />
    <Services />
</div>