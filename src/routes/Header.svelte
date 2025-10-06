
<script lang="ts">
	import logo from '$lib/assets/logo.png';
    import { onMount, onDestroy } from "svelte";

    let scrollY = $state(0);



    onMount(() => {
        const handleScroll = () => {
            scrollY = window.scrollY;
            console.log(opacity)
        };
        window.addEventListener("scroll", handleScroll);

        return () => {
            window.removeEventListener("scroll", handleScroll);
        }
    });


    // Calculate opacity based on scroll distance (0 → 1)
    let opacity = $derived(scrollY/1000);
    

</script>

<header id="header" class="align-baseline block shadow-[0_1px_2px_0_rgba(0,0,0,0.075)] text-inherit cursor-default 
         text-[0.8em] left-0 py-4 px-6 fixed top-0 w-full z-[10000]" style:background-color={`rgba(255, 255, 255, ${opacity})`}>
    <h1 class="font-black m-0" id="logo"><a href="/">Twenty <span class="font-light">by HTML5 UP</span></a></h1>
    <nav class="tracking-[0.075em] absolute right-6 uppercase top-3" id="nav">
        <ul class="list-none pl-0">
            <li class="inline-block ml-1.5em pl-0"><a href="/">Welcome</a></li>
            <li class="inline-block ml-1.5em pl-0"><a href="#">Sign Up</a></li>
        </ul>
    </nav>
</header>