<script>
    import { onMount } from "svelte";
    import { gsap } from "gsap";
    import { ScrollTrigger } from "gsap/ScrollTrigger";
    import Lenis from "lenis";
    import "lenis/dist/lenis.css";
    import "./layout.css";
    import favicon from "$lib/assets/favicon.svg";
    import Header from "$lib/components/header.svelte";
    import Cursor from "$lib/components/Cursor.svelte";

    let { children } = $props();

    onMount(() => {
        gsap.registerPlugin(ScrollTrigger);

        // Lenis'i başlat (Smooth Scrolling)
        const lenis = new Lenis({
            autoRaf: true,
            duration: 1.2,
            easing: (t) => Math.min(1, 1.001 - Math.pow(2, -10 * t)),
            direction: "vertical",
            gestureDirection: "vertical",
            smooth: true,
            smoothTouch: false,
            touchMultiplier: 2,
        });

        // GSAP ScrollTrigger'ın Scroll güncellemelerini Lenis'e bağla
        lenis.on("scroll", ScrollTrigger.update);

        gsap.ticker.add((time) => {
            lenis.raf(time * 1000);
        });

        gsap.ticker.lagSmoothing(0);

        return () => {
            lenis.destroy();
            gsap.ticker.remove(lenis.raf);
        };
    });
</script>

<svelte:head>
    <link rel="icon" href={favicon} />
</svelte:head>

<Cursor />
<Header />

<main class="app-wrapper">
    {@render children()}
</main>
