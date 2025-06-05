<script>
    import leah from "$lib/images/LilLeahPNG.png";
    import SimpleButton from "$lib/SimpleButton.svelte";
    import SmallButton from "$lib/SmallButton.svelte";

    let icarusLink = "https://linktr.ee/IcarusGameDev";

    let { showGames, showArt, showAbout } = $props();

    import revealSound from "$lib/Sounds/_click.mp3"


</script>

<div class="center">
    <div class="leftSide">
        <div class="leahMoveArea">
            <img src={leah} alt="leah" class="lilLeah" />
        </div>
    </div>
    <div class="rightSide">
        <h2>Hello!</h2>
        <p>
            I'm Ashley, a game developer, designer, and artist. I love creating
            things and want to give people cool experiences with my games. <br
            />
            I'm currently a programmer at
            <a href={icarusLink} target="_blank">Icarus Digital</a> and work on solo
            projects in my free time
        </p>
        <br /><br /><br />
        <div class="linkButtons">
            <div class="linkButtonsCenter">
                <SimpleButton
                    button_text="Games"
                    OnClick={showGames}
                    sound = {revealSound}
                />
                <SimpleButton
                    button_text="Art"
                    OnClick={showArt}
                    sound = {revealSound}
                    href={"https://www.instagram.com/bnueyy/"}
                    target="_blank"
                />
                <SimpleButton
                    button_text="About"
                    OnClick={showAbout}
                    sound = {revealSound}
                />
                <br />
                <div class="fileButton">
                    <div class="fileButtonCenter">
                        <SmallButton button_text="Other Random Stuff I've Made", href="/files"/>

                    </div>
                </div>

            </div>
        </div>
    </div>
</div>

<style>
    .center {
        margin: 100px auto;
        width: 70%;
        height: auto;
        background: #d1e8c1;
        border: 2px solid #33462a;
        padding: 10px;
        border-radius: 20px;
        display: grid;
        grid-template-areas: "image text";
        grid-template-columns: 40% 60%;
        gap: 5px;
    }

    .center > div {
        height: 500px;
    }

    .center > div.leftSide {
        grid-area: image;
    }

    .center > div.rightSide {
        grid-area: text;
    }

    .lilLeah {
        height: 400px;
        align-self: center;
        padding: 7%;
        width: auto;
        animation: rotate 4s infinite;
        animation-delay: -500ms;
        animation-timing-function: ease-in-out;
        position: relative;
    }

    .leahMoveArea {
        height: 10%;
        translate: 0 -30%;
    }

    .rightSide > h2,
    p {
        margin: 20px;
        text-align: center;
    }

    .linkButtons {
        margin: auto;
        display: flex;
    }

    .linkButtonsCenter {
        margin: auto;
    }

    @keyframes rotate {
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

    .fileButton {
        display: flex;
        margin:auto;
    }
    .fileButtonCenter {
        margin: auto;
    }
</style>
