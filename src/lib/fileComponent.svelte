<script>
    // Props
    let { data, has_download} = $props();


     function downloadData()
     {
        var blob = new Blob([data.href]);
        var name = data.title

        var a = document.createElement('a');

        document.body.append(a);

        a.download = name;

        a.href = URL.createObjectURL(blob);

        a.click();

        a.remove();
    }

</script>

<div class="center">
    <div class="leftSide">
        <a href="#" target="_blank" onclick={downloadData}>
            <img
                src={data.img.src}
                class="fileImage"
                alt={data.img.alt}
            />
        </a>
    </div>
    <div class="rightSide">
        <div class="titleDateArea">
            <a href="#" class="links" target="_blank" onclick={downloadData}>
                <div class="titleArea">
                    <h2>{data.title}</h2>
                </div>
            </a>

            <div class="dateArea">
                <h4>{data.date}</h4>
            </div>
        </div>
        <hr>
        <div class="descArea">
            <h3>{@html data.description}</h3>
        </div>
    </div>
</div>

<style>
    .center {
        width: 70%;
        height: auto;
        margin: 20px auto;
        background: #d1e8c1;
        border: 2px solid #33462a;
        padding: 10px;
        border-radius: 20px;
        display: grid;
        grid-template-areas: "image text";
        grid-template-columns: 20% 80%;
        gap: 5px;
    }

    .fileImage {
        width: 100%;
        border-radius: 20px;
        border: 2px solid #33462a;
    }

    .titleDateArea {
        display: grid;
        width: 100%;
        height: auto;
        grid-template-areas: "title date";
        grid-template-columns: 90% 10%;
        gap: 5px;
    }

    h2 {
        margin: 0px 20px;
    }
    h4 {
        margin: 20px;

        float: right;
    }
    h3 {
        margin: 20px;
    }
    hr {
        margin: 0px 20px;
    }

    .links {
        text-decoration: none;
    }
</style>
