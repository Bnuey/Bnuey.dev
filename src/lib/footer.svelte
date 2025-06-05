<script lang="ts">
    import itch from "$lib/images/Itch.png";
    let itchLink = "https://bnuey.itch.io/";

    import bsky from "$lib/images/Bsky.png";
    let bskyLink = "https://bsky.app/profile/bnuey.dev";

    import instagram from "$lib/images/Instagram.png";
    let instagramLink = "https://www.instagram.com/bnueyy/";

    import SocialLink from "$lib/sociallogo.svelte";
</script>

<hr class="grrrrr"/>

<!-- Itch.io Link -->
<div class="footer">
    <div class="center">
        <SocialLink href={itchLink} src={itch} alt="Itch.io" />
        <SocialLink href={bskyLink} src={bsky} alt="Bluesky"/>
        <SocialLink href={instagramLink} src={instagram} alt="Instagram"/>
    </div>
</div>

<style>
    .footer {
        padding: 10px;
        width: 50%;
        margin:auto;
        display: flex;
    }

    .center {
        margin:auto;
    }

    .grrrrr {
        margin: 50px auto 0px;
    }
</style>
