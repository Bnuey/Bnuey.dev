<script>
    import { injectAnalytics } from '@vercel/analytics/sveltekit'

    import Games from "$lib/Games.svelte";
    import IndexAbout from "$lib/IndexAbout.svelte";
    import Footer from "$lib/footer.svelte";
    import ClairePettingGame from "../ClairePettingGame.svelte";
    import PageTitle from "$lib/PageTitle.svelte";
    import Construction from "$lib/Construction.svelte";
    import { fly } from "svelte/transition";
    import AboutMain from "$lib/AboutMain.svelte";
    import {
        scrollRef,
        scrollTo,
        scrollTop,
        scrollElement,
        setGlobalOptions,
    } from "svelte-scrolling";
    import { cubicOut, elasticOut, sineOut } from "svelte/easing";

    import { building } from "$app/environment"
    import ArtGallery from '$lib/ArtGallery.svelte';

    if (!building) {
        injectAnalytics();
    }

    let revealArt = false;
    let revealGames = false;
    let revealAbout = false;

    setGlobalOptions({
        duration: 400,
        easing: cubicOut,
        offset: -100
    });

    function ShowGames() {
        SetAllFalse();
        revealGames = true;
        scrollElement("Games");
    }

    function ShowArt() {
        SetAllFalse();
        revealArt = true;
        scrollElement("Art");
    }

    function ShowAbout() {
        SetAllFalse();
        revealAbout = true;
        scrollElement("About");
    }

    function SetAllFalse() {
        revealArt = false;
        revealGames = false;
        revealAbout = false;
    }
</script>

<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link
    href="https://fonts.googleapis.com/css2?family=Amatic+SC:wght@400;700&family=Sour+Gummy:ital,wght@0,100..900;1,100..900&display=swap"
    rel="stylesheet"
/>

<PageTitle back="false" />
<IndexAbout showGames={ShowGames} showArt={ShowArt} showAbout={ShowAbout} />

<section use:scrollRef={"Games"} />
<section use:scrollRef={"Art"} />
<section use:scrollRef={"About"} />
{#if revealGames}
    <div in:fly={{ y: -200, duration: 500 }}>
        <Games />
    </div>
{/if}
{#if revealArt}
    <div in:fly={{ y: -200, duration: 500 }}>
        <ArtGallery/>
    </div>
{/if}
{#if revealAbout}
    <div in:fly={{ y: 0, duration: 500 }}>
        <AboutMain />
    </div>
{/if}
<Footer />

<style>
    :global(body) {
        background-color: #e0f8cf;
    }

    :global(p, h1, h2, h3, h4) {
        font-family: "Sour Gummy", monospace;
        color: #33462a;
        font-weight: 850;
    }

    :global(p) {
        font-size: 1.3em;
    }

    :global(h4) {
        font-size: 1.6em;
    }

    :global(h3) {
        font-size: 2em;
    }

    :global(h2) {
        font-size: 3em;
    }

    :global(h1) {
        font-size: 4em;
    }

    :global(html) {
        scroll-behavior: smooth;
        -ms-overflow-style: none; /* IE and Edge */
        scrollbar-width: none; /* Firefox */
    }

    :global(a:hover, label > h3:hover, a > h2:hover) {
        color: #739e5e;
    }

    :global(hr) {
        color: #33462a;
    }

    /* Hide scrollbar for Chrome, Safari and Opera */
    html::-webkit-scrollbar {
        display: none;
    }

    /* Hide scrollbar for IE, Edge and Firefox */
    html {
        -ms-overflow-style: none; /* IE and Edge */
        scrollbar-width: none; /* Firefox */
    }
</style>
