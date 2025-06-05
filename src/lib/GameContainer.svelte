<script lang="ts">
    import SimpleButton from "$lib/SimpleButton.svelte";
    import GameAnecdote from "$lib/GameAnecdote.svelte";
    import ClickSound from "$lib/Sounds/_click.mp3"
    export let data;
</script>

<section id={data.title}>
    <div class="center">
        <div class="leftSide">
            <a href={data.href} target="_blank">
                <img src={data.img.src} alt={data.img.alt} class="gameImage" />
            </a>
        </div>
        <div class="rightSide">
            <h1>{data.title}</h1>
            <h4>{data.date}</h4>
            <br />
            <h3>{@html data.info}</h3>
            {#if data.info != ""}
                <br /><br />
            {/if}
            <h4>{@html data.description}</h4>

            <div class="buttonAnchor">
                <div class="buttonArea">
                    <div class="buttonCenter">
                        <SimpleButton
                            button_text="Play"
                            href={data.href}
                            target="_blank"
                            sound = {ClickSound}
                            OnClick = ""
                        />
                    </div>
                </div>
            </div>
        </div>
    </div>
    <GameAnecdote anecdote={data.anecdote} />
</section>

<style>
    .gameImage {
        border-radius: 20px;
        width: 640px;
        height: auto;
        border: 2px solid #33462a;
    }

    .center {
        margin: 50px auto 10px;
        width: 85%;
        height: auto;
        background: #d1e8c1;
        border: 2px solid #33462a;
        border-radius: 20px;
        display: grid;
        grid-template-areas: "image text";
        grid-template-columns: 45% auto;
        gap: 5px;
        padding: 20px;
    }

    .center > div.leftSide {
        grid-area: image;
    }

    .center > div.rightSide {
        grid-area: text;
    }

    h1,
    h2,
    h3,
    p,
    h4 {
        margin: 5px;
        padding: 0px;
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

    .buttonArea {
        display: flex;
        position: relative;
    }
    .buttonAnchor {
        position: absolute;
        bottom: 0px;
        width: 100%;
    }

    .buttonCenter {
        margin: auto;
    }

    section {
        scroll-margin-top: 100px;
    }

    .rightSide {
        position: relative;
    }
</style>
