<script lang="ts">
    import claire from "$lib/images/claire.jpg";

    let pet_amount = 0;

    let vel = 0;

    function pet_claire() {
        vel++;
        if (vel > 100) {
            pet_amount++;
            vel = 0;
        }

    }
</script>

<div class="center">
    <div onmousemove={pet_claire}>
        <img src={claire} alt="Claire" class="clairebear"/>
    </div>
<h1>{pet_amount}</h1>
</div>

<style>
    .center {
        margin: auto;
        width: 50%;
        border: 3px solid green;
        padding: 10px;
    }
    .clairebear {
        height: 400px;
        width: auto;
        margin: auto;
    }
</style>
