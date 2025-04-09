<script lang="ts">
    import '../app.css';

    let scroll = $state(0);
    $effect(() => {
        console.log(scroll);
    })
</script>

<svelte:window bind:scrollY={scroll} />

<main>
    <h1 class="title">just how fast can you <span class="scroll">scroll</span>?</h1>
    <div class="scroll-container">
        <div>you have <b>8s</b>.</div>
        how far can you scroll?
    </div>
    <div class="leaderboard">
        <h2>Leaderboard</h2>
    </div>
</main>
  
<style lang="scss">
    $primary: #FDA920;

    // Dark
    $stroke: #696969; // funny
    $accent: #444;
    $bg: #333;
    $text: #fff;

    // Light
    $stroke-light: #A8A8A8;
    $accent-light: #EEE;
    $text-light: #000;
    $bg-light: #e5e5e5;

    main {
        width: 100vw;
        height: 100vh;
        background-color: $bg;
        color: $text;
        padding: 1rem;
        font-family: 'DM Mono', sans-serif;
        font-size: 1.2rem;
        // line-height: 1.5;

        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 80px;
        overflow: hidden;


        @media (prefers-color-scheme: light) {
            background-color: $bg-light;
            color: $text-light;
        }
    }
    .title {
        // font-size: 2.5rem;
        background-color: $primary;
        color: transparent;
        -webkit-background-clip: text;
        -moz-background-clip: text;
        background-clip: text;
        text-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
        font-size: min(8vw, 75px);
        font-weight: 700;
        text-align: center;
        // margin-bottom: 1rem;
    }
    .scroll-container {
        background-color: $accent;
        color: #aaa;
        font-size: 48px;
        font-weight: 500;
        text-align: center;
        // width: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        flex: 1;
        width: 100%;

        
        max-width: 800px;
        max-height: 400px;
        margin: 0 1em;
        border-radius: 32px;
        border: 1px solid $stroke;
        box-shadow: 0px 0px 16px 1px rgba(0, 0, 0, 0.25) inset;

        @media (prefers-color-scheme: light) {
            background-color: $accent-light;
            color: $stroke-light;
            border: 1px solid $stroke-light;
        }
    }
    .leaderboard {
        color: $text;
        background-color: $accent;
        font-size: 24px;
        transform: rotate(-3deg);
        filter: drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.25));
        border: 1px solid $stroke;
        padding: 1rem;
        border-radius: 32px;
        display: flex;
        align-items: flex-start;
        justify-content: flex-start;
        width: calc(100% - 2rem);
        max-width: 800px;
        bottom: -4rem;
        position: fixed;
        padding-bottom: 6rem;
        

        h2 {
            padding: 0;
            margin: 0;
        }

        @media (prefers-color-scheme: light) {
            background-color: $accent-light;
            color: $text-light;
            border: 1px solid $stroke-light;
        }
    }
</style>