<script>
    import Gallery from 'svelte-image-gallery';

    function handleClick(e) {
        console.log(e.detail.src);
    }

    import balcony from '$lib/Art/The Balcony Place.gif'
    import stoat from '$lib/Art/stoat.gif'
    import indies from '$lib/Art/Indies playing euchre final.png'
    import niko from '$lib/Art/nino3.png'
    import switch2 from '$lib/Art/switch.png'
    import spacenshid from '$lib/Art/space-background-2.gif'
    import key from '$lib/Art/key.gif'
    import walle from '$lib/Art/wallee.png'
    import haru from '$lib/Art/haru.png'
    import lightbulb from '$lib/Art/lightbulb.png'
    import bellie from '$lib/Art/bellie.gif'
    import abstract from '$lib/Art/abstract.gif'
    import ninja1 from '$lib/Art/ninjacube1.gif'
    //import ninja2 from '$lib/art/ninjacubenruben.gif'
    import necoarc from '$lib/Art/necoarc.jpg'
    import piano from '$lib/Art/Pianberrtro.png'
    import bobbleloading from '$lib/Art/bobbleloading.gif'
    import bobbleB from '$lib/art/bobbleb.gif'
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
        <img src={stoat}/>
        <img src={indies}/>
        <img src={niko}/>
        <img src={switch2}/>
        <img src={spacenshid}/>
        <img src={key}/>
        <img src={walle}/>
        <img src={haru}/>
        <img src={lightbulb}/>
        <img src={bellie}/>
        <img src={abstract}/>
        <img src={ninja1}/>
        <!--<img src={ninja2}/>-->
        <img src={necoarc}/>
        <img src={piano}/>
        <img src={bobbleloading}/>
        <img src={bobbleB}/>
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
