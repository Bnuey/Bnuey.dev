<script lang="ts">
    import me from "$lib/images/me.jpg";
</script>

<div class="center">
    <div class="leftSide">
        <div class="moveArea">
            <img src={me} alt="Ashley" class="ashley" />
        </div>
    </div>
    <div class="rightSide">
        <h2>So you wanna know more?</h2>
        <p>
            I'm a 20y/o Game Designer, Programmer, Artist, Video Editor, 3D
            Modeler, and more. I always love learning new skills and have a lot
            of experience with many different ways of expressing myself
            <br /><br />Game Development is the perfect excuse to put all my
            different skills together into one project as well as give people
            cool experiences they wouldn't have otherwise. I'm currently a
            university student majoring in Game Development in Canada
            <br /><br />I've used and am familiar with, Godot, Unity, Blender,
            Premeire Pro, After Effects, C#, Java, GDScript, HTML, CSS, Javascript &
            Svelte.
            <br />This website was coded by hand using Svelte, you can
            find source
            <a href="https://github.com/Bnuey/Bnuey.dev" target="_blank">here</a
            > in case you wanna judge my code.<br>(Web dev is not my specialty)
        </p>
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

    .moveArea {
        height: 10%;
        translate: 0 -30%;
    }

    .ashley {
        border-radius: 20px;
        height: 400px;
        align-self: center;
        padding: 7%;
        width: auto;
        animation: rotate 4s infinite;
        animation-delay: -500ms;
        animation-timing-function: ease-in-out;
        position: relative;
    }

    .rightSide > p,
    h2 {
        margin: 20px;
        text-align: center;
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
</style>
