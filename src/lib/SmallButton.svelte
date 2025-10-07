<script lang="ts">
    import hoverSound from "$lib/Sounds/hover.mp3";
    import clickSound from "$lib/Sounds/click.mp3";
    import backSound from "$lib/Sounds/back.mp3";

    let { button_text, href, back = false, target = "", sound = clickSound} = $props();

    let audio = null;

    let hovered = $state(false);
    let clicked = $state(false);



    function Hover() {
        hovered = true;
        PlaySound(hoverSound, 0.2);
    }

    function UnHover() {
        hovered = false;
    }

    function Clicked() {
        clicked = true;

        PlaySound(sound, .3);
    }

    function PlaySound(sound = "", volume = 1.0) {
        audio = new Audio();
        audio.src = sound;
        audio.volume = volume;
        audio.load();
        audio.play();
    }
</script>

<a {href} {target}>
    <button
        class={["button", { hovered, clicked }]}
        onmouseenter={Hover}
        onmouseleave={UnHover}
        onclick={Clicked}
    >
        <p class="buttonText">{button_text}</p>
    </button>
</a>

<style>
    .button {
        background-color: #33462a;
        width: auto;
        height: 40px;
        border-radius: 20px;
        border-style: solid;
        transform: scale(1);
        transition: transform 0.4s;
    }

    .button.hovered {
        transform: scale(1.2);
    }

    .button.clicked {
        transform: scale(1.4);
    }

    .buttonText {
        color: #e0f8cf;
        margin: auto;
    }
</style>
