
<script lang="ts">
	import logo from '$lib/assets/logo.png';
    import { onMount, onDestroy } from "svelte";
	import { sineOut } from 'svelte/easing';
    import {
        blur,
        crossfade,
        draw,
        fade,
        fly,
        scale,
        slide
    } from 'svelte/transition';


    const [send, receive] = crossfade({
        duration: 400,
        easing: sineOut,
    });

    let y= $state(0);

    function onScroll(){
        console.log($state.snapshot(y));
    }

</script>


<svelte:window  bind:scrollY={y} onscroll={onScroll} />


{#snippet headerContent()}
<h1 class="font-black m-0" id="logo"><a href="/">Twenty <span class="font-light">by HTML5 UP</span></a></h1>
<nav class="tracking-[0.075em] absolute right-6 uppercase top-3" id="nav">
    <ul class="list-none pl-0">
        <li class="inline-block ml-1.5em pl-0"><a href="/">Welcome</a></li>
        <li class="inline-block ml-1.5em pl-0"><a href="#">Sign Up</a></li>
    </ul>
</nav>
{/snippet}

{#if y > 1000}
    <header in:receive={{ key: "header"}} out:send={{ key: "header"}} id="header" class="align-baseline bg-white block shadow-[0_1px_2px_0_rgba(0,0,0,0.075)] text-inherit cursor-default text-[0.8em] left-0 py-4 px-6 fixed top-0 w-full z-[10000]">
        {@render headerContent()}
    </header>
{:else}
        <header in:receive={{ key: "header"}} out:send={{ key: "header"}} id="header" class="align-baseline block text-inherit cursor-default text-[0.8em] left-0 py-4 px-6 fixed top-0 w-full z-[10000]">
        {@render headerContent()}
    </header>
{/if}