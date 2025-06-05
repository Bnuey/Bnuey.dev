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
    import CelesteResourcepack from "$lib/FileJS/Celeste Resourcepack.js";
    import NinjaCubePapercraft from "$lib/FileJS/NinjaCubePapercraft.js";

</script>

<PageTitle title="Files & Stuff"/>
<FileComponent
    data={AmIAlirght}
/>
<FileComponent
    data={CameraSpeedMod}
/>
<FileComponent
    data={MinimalArmor}
/>
<FileComponent
    data={CelesteResourcepack}
/>
<FileComponent
    data={NinjaCubePapercraft}
/>

<Footer/>

<style>

</style>


