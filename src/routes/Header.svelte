
<script lang="ts">
	import logo from '$lib/assets/logo.png';
	import { sineOut } from 'svelte/easing';
    import {
        crossfade,
    } from 'svelte/transition';

    // This creates the variables to have a fade effect when transitioning between header styles.
    const [send, receive] = crossfade({
        duration: 400,
        easing: sineOut,
    });

    // This y is bound to the 'scrollY' value of the client webpage. This is then used in html to display differernt headers at different parts of the page
    let y= $state(0);
</script>


<svelte:window  bind:scrollY={y} />

<!-- Header content is repeated for the purpose of animating it.-->
{#snippet headerContent()}
<h1 class="font-black m-0" id="logo"><a href="/">Twenty <span class="font-light">by HTML5 UP</span></a></h1>
<nav class="tracking-[0.075em] absolute right-6 uppercase top-3" id="nav">
    <ul class="list-none pl-0">
        <li class="inline-block ml-1.5em pl-0"><a href="/">Welcome</a></li>
        <li class="inline-block ml-1.5em pl-0"><a href="#my-approach">Sign Up</a></li>
    </ul>
</nav>
{/snippet}

<!-- Two headers, the first is white, the second is translucent. They transition into eachother at   -->
{#if y > 1000}
    <header in:receive={{ key: "header"}} out:send={{ key: "header"}} id="header" class="align-baseline bg-white block shadow-[0_1px_2px_0_rgba(0,0,0,0.075)] text-inherit cursor-default text-[0.8em] left-0 py-4 px-6 fixed top-0 w-full z-[10000]">
        {@render headerContent()}
    </header>
{:else}
        <header in:receive={{ key: "header"}} out:send={{ key: "header"}} id="header" class="align-baseline block text-inherit cursor-default text-[0.8em] left-0 py-4 px-6 fixed top-0 w-full z-[10000]">
        {@render headerContent()}
    </header>
{/if}