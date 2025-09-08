<script lang="ts">
    let { anecdote } = $props();


    import GameAnecdote from "./GameAnecdote.svelte";
    import { fly } from "svelte/transition";

    import show from "$lib/Sounds/show.mp3";
    import hide from "$lib/Sounds/hide.mp3";

    let audio = null;
    let visible = $state(false);

    function Clicked() {
        if (visible) { PlaySound(hide, 0.5)}
        else { PlaySound(show, 0.5)}
    }

    function PlaySound(sound = "", volume = 1.0) {
        audio = new Audio();
        audio.src = sound;
        audio.volume = volume;
        audio.load();
        audio.play();
    }
</script>

<div class="main">
    <div class="centerAlign">
        <label>
            <input type="checkbox" bind:checked={visible} on:click={Clicked}/>
            {#if visible}
                <h3>Hide Anecdote</h3>
            {:else}
                <h3>Show Anecdote</h3>
            {/if}
        </label>

        {#if visible}
            <div transition:fly={{ y: -50, duration: 200 }}>
                <p>
                    {@html anecdote}
                </p>
            </div>
        {/if}
    </div>
</div>

<style>
    .main {
        background: #d1e8c1;
        border: 2px solid #33462a;
        border-radius: 20px;
        width: 85%;
        margin: auto;
        padding: 20px;
        text-align: center;
    }

    .centerAlign {
        width: 100%;
    }

    input {
        position: absolute;
        opacity: 0;
        cursor: pointer;
        height: 0;
        width: 0;
    }

    h3 {
        margin: 0px;
    }
</style>
