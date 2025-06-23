<script>
    import Gallery from '$lib/Gallery.svelte';

    function handleClick(e) {
        console.log(e.detail.src);
    }

    import balcony from '$lib/Art/The Balcony Place.gif'
    import stoat from '$lib/Art/inscryption.webm'
    import indies from '$lib/Art/Indies playing euchre final.png'
    import niko from '$lib/Art/nino3.png'
    import switch2 from '$lib/Art/switch.png'
    import spacenshid from '$lib/Art/space.webm'
    import key from '$lib/Art/key.webm'
    import walle from '$lib/Art/wallee.png'
    import haru from '$lib/Art/haru.png'
    import lightbulb from '$lib/Art/lightbulb.png'
    import bellie from '$lib/Art/bellie.webm'
    import abstract from '$lib/Art/abstract.webm'
    import ninja1 from '$lib/Art/ninjacube.webm'
    import ninja2 from '$lib/Art/ninjacube2.webm'
    import necoarc from '$lib/Art/necoarc.jpg'
    import piano from '$lib/Art/Pianberrtro.png'
    import bobbleloading from '$lib/Art/phone.webm'
    import bobbleB from '$lib/Art/bobbleB.webm'
    import unfinishedhouse from '$lib/Art/unfinishedhouse.jpg'
    import theplace from '$lib/Art/theplace.jpg'
    import text from '$lib/Art/Text.png'
    import upsidown from '$lib/Art/Upsidown.png'
    import circle from '$lib/Art/Circle.png'
    import coke from '$lib/Art/Coke.png'
</script>

<div class="center">
    <Gallery on:click={handleClick} maxColumnWidth={350} hover={true} gap={15}>
        <img src={balcony}/>
        <video
            autoplay
            loop
            muted
            height="100%"
            src={stoat}
        ></video>
        <img src={indies}/>
        <img src={niko}/>
        <img src={switch2}/>
        <video
            autoplay
            loop
            muted
            height="100%"
            src={spacenshid}
        ></video>
        <video
            autoplay
            loop
            muted
            height="100%"
            src={key}
        ></video>
        <img src={walle}/>
        <img src={haru}/>
        <img src={lightbulb}/>
        <video
            autoplay
            loop
            muted
            height="100%"
            src={bellie}
        ></video>
        <video
            autoplay
            loop
            muted
            height="100%"
            src={abstract}
        ></video>
        <video
            autoplay
            loop
            muted
            height="100%"
            src={ninja1}
        ></video>
        <video
            autoplay
            loop
            muted
            height="100%"
            src={ninja2}
        ></video>
        <img src={necoarc}/>
        <img src={piano}/>
        <video
            autoplay
            loop
            muted
            height="100%"
            src={bobbleloading}
        ></video>
        <video
            autoplay
            loop
            muted
            height="100%"
            src={bobbleB}
        ></video>
        <img src={unfinishedhouse}/>
        <img src={theplace}/>
        <img src={text}/>
        <img src={upsidown}/>
        <img src={circle}/>
        <img src={coke}/>
    </Gallery>
</div>

<style>
    .center {
        margin: auto;
        display: flex;
        width: 90%;
        background: #d1e8c1;
        border: 2px solid #33462a;
        padding: 20px;
        border-radius: 20px;
    }

    .center > img {
        border-radius: 20px;
    }

    .artGallery {
        background: black;
        width: 70%;
    }
</style>
