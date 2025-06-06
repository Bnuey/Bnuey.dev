<script>
    // Props
    let { data } = $props();
</script>

<div class="center">
    <div class="leftSide">
        <a href={data.href} target="_blank">
            <img
                src={data.img.src}
                class="fileImage"
                alt={data.img.alt}
            />
        </a>
    </div>
    <div class="rightSide">
        <div class="titleDateArea">
            <a href={data.href} class="links">
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
