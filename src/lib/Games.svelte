<script>
    import GameContainer from "$lib/GameContainer.svelte";

    // Games
    import NotQuiteRight from "$lib/Games/NotQuiteRight.js";
    import UmbrellaCat from "$lib/Games/UmbrellaCat.js";
    import QuestionHeir from "$lib/Games/QuestionHeir.js";
    import Sacriforest from "$lib/Games/Sacriforest.js";
    import RoadyCar from "$lib/Games/RoadyCar.js";
    import BobbleVsTheGame from "$lib/Games/BobbleVsTheGame.js";
    import UPCARD from "$lib/Games/UPCARD.js";
</script>

<GameContainer data={UPCARD} />
<GameContainer data={NotQuiteRight} />
<GameContainer data={UmbrellaCat} />
<GameContainer data={QuestionHeir} />
<GameContainer data={Sacriforest} />
<GameContainer data={RoadyCar} />
<GameContainer data={BobbleVsTheGame} />
