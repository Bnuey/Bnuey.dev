<script lang="ts">
    import _hoverSound from "$lib/Sounds/hover.mp3";
    import _clickSound from "$lib/Sounds/click.mp3";

    let { button_text, OnClick, back = false, sound: clickSound = _clickSound, hoverSound = _hoverSound, href ="", target=""} = $props();

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
        PlaySound(clickSound, 0.5);
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
    on:mouseenter={Hover}
    on:mouseleave={UnHover}
    on:click={Clicked}
    on:click={OnClick}
>
    <h2 class="buttonText">{button_text}</h2>
    </button>
</a>

<style>
    .button {
        background-color: #33462a;
        width: 150px;
        height: 100px;
        border-radius: 20px;
        border-style: solid;
        margin: auto;
        transform: scale(1);
        transition: transform 0.4s;
        margin: 10px 20px;
    }

    .button.hovered {
        transform: scale(1.2);
    }

    .buttonText {
        color: #e0f8cf;
        margin: auto;
    }
</style>
