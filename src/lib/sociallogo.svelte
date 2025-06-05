<script lang="ts">
    let { href, src, alt } = $props();

    let audio = null;

    let hovered = $state(false);
    let clicked = $state(false);

    import hoverSound from "$lib/Sounds/hover.mp3";
    import clickSound from "$lib/Sounds/click.mp3";

    function Hover() {
        hovered = true;
        PlaySound(hoverSound, .5);
    }

    function UnHover() {
        hovered = false;
    }

    function Clicked() {
        clicked = true;
        PlaySound(clickSound, 1);
    }

    function PlaySound(sound = "", volume = 1.0) {
        audio = new Audio();
        audio.src = sound;
        audio.volume = volume;
        audio.load();
        audio.play();
    }

</script>


<a {href} target="_blank" onmouseenter={Hover} onmouseleave={UnHover} onclick={Clicked}>
    <img {src} class={["sociallogo", { hovered }]} {alt}/>
</a>

<style>
    .sociallogo {
        width: 64px;
        height: 64px;
        transform: scale(1);
        transition: transform 0.4s;
    }


    .sociallogo.hovered {
        transform: scale(1.1);
    }
</style>
