<script lang="ts">
    import SimpleButton from "$lib/SimpleButton.svelte";
    let { title = "Bnuey.dev", back = true } = $props();

    import backSound from "$lib/Sounds/back.mp3"
    import SmallButton from "$lib/SmallButton.svelte";
</script>

<div class="anim_area">
    <div class="title">
        <h1>
            {title}
        </h1>
        {#if back == true}
            <div class="backButtonArea">
                <div class="buttonCenter">
                    <SmallButton button_text="< Back" href="/" back=true sound={backSound}/>
                </div>
            </div>
        {/if}
    </div>
</div>

<style>
    .title {
        text-align: center;
        animation: updown 4s infinite;
        animation-delay: 0ms;
        animation-timing-function: ease-in-out;
        position: relative;
    }

    .anim_area {
        margin: 20px 0px;
        height: 50px;
        margin: 0px 0px 150px;
    }

    @keyframes updown {
        0% {
            top: 0%;
        }
        50% {
            top: 100%;
        }
        100% {
            top: 0%;
        }
    }

    .backButtonArea {
        margin: 0px auto;
        width: 10%;
        display: flex;
    }

    .buttonCenter {
        margin: 0px auto;
    }

    h1 {
        margin: 0px;
    }
</style>
