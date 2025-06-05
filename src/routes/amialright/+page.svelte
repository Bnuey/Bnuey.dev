<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Amatic+SC:wght@400;700&family=Sour+Gummy:ital,wght@0,100..900;1,100..900&display=swap" rel="stylesheet">

<script>
    import PageTitle from "$lib/PageTitle.svelte";
</script>

<div class="center">
    <h1>You are alright.</h1>
</div>

<style>
    .center{
        margin: auto;
    }

    h1 {
        align-self: center;
        text-align: center;
    }

    :global(body) {
        background-color: #e0f8cf;
    }

    :global(p, h1, h2, h3, h4) {
        font-family: "Sour Gummy", monospace;
        color: #33462a;
        font-weight:850;
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

    :global(a:hover, label > h3:hover) {
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
