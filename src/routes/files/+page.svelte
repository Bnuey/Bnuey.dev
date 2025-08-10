<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Amatic+SC:wght@400;700&family=Sour+Gummy:ital,wght@0,100..900;1,100..900&display=swap" rel="stylesheet">

<script>
    import PageTitle from "$lib/PageTitle.svelte";
    import FileComponent from "$lib/fileComponent.svelte";
    import Footer from "$lib/footer.svelte";

    import AmIAlirght from "$lib/FileJS/AmIAlright.js"
    import CameraSpeedMod from "$lib/FileJS/CameraSpeedMod.js";
    import MinimalArmor from "$lib/FileJS/MinimalArmor.js";
    import MinimalArmor2 from "$lib/FileJS/MinimalArmor 1.21.4.js";
    import CelesteResourcepack from "$lib/FileJS/Celeste Resourcepack.js";
    import NinjaCubePapercraft from "$lib/FileJS/NinjaCubePapercraft.js";
    import TileLockMod from "$lib/FileJS/LockTilesKeybind.js";
    import LeahTheBunny from "$lib/FileJS/LeahForSM64";


</script>

<PageTitle title="Files & Stuff"/>
<FileComponent
    data={TileLockMod}
    has_download={false}
/>
<FileComponent
    data={LeahTheBunny}
    has_download={true}
    target=''
/>
<FileComponent
    data={CameraSpeedMod}
    has_download={false}
/>
<FileComponent
    data={AmIAlirght}
    has_download={false}
/>
<FileComponent
    data={MinimalArmor2}
    has_download={true}
    target=''
/>
<FileComponent
    data={MinimalArmor}
    has_download={true}
    target=''
/>
<FileComponent
    data={CelesteResourcepack}
    has_download={true}
    target=''
/>
<FileComponent
    data={NinjaCubePapercraft}
    has_download={true}
    target=''
/>

<Footer/>

<style>

</style>


