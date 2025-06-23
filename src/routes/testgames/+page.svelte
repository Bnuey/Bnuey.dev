<script lang="ts">

</script>

<div class="container">
    <div class="box"></div>
    <div class="box"></div>
    <div class="box"></div>
    <div class="box"></div>
</div>



<style>

    .container {
        display: grid;
        grid-template-columns: auto auto auto;
        width: auto;
    }

    .box {
        width:100px;
        height: 100px;
        background: #73c1fc;
        border-radius: 10px;
    }

    :global(body) {
        background-color: #2e2e2e;
    }

    :global(p, h1, h2, h3, h4) {
        font-family: "Sour Gummy", monospace;
        color: #33462a;
        font-weight: 850;
    }

    :global(p) {
        font-size: 1.3em;
    }

    :global(h4) {
        font-size: 1.6em;
    }

    :global(h3) {
        font-size: 2em;
    }

    :global(h2) {
        font-size: 3em;
    }

    :global(h1) {
        font-size: 4em;
    }

    :global(html) {
        scroll-behavior: smooth;
        -ms-overflow-style: none; /* IE and Edge */
        scrollbar-width: none; /* Firefox */
    }

    :global(a:hover, label > h3:hover, a > h2:hover) {
        color: #739e5e;
    }

    :global(hr) {
        color: #33462a;
    }

    /* Hide scrollbar for Chrome, Safari and Opera */
    html::-webkit-scrollbar {
        display: none;
    }

    /* Hide scrollbar for IE, Edge and Firefox */
    html {
        -ms-overflow-style: none; /* IE and Edge */
        scrollbar-width: none; /* Firefox */
    }
</style>