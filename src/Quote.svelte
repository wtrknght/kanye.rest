<script>
    import { fly } from "svelte/transition";

    let tweet_url;

    async function getQuote() {
        const response = await fetch("https://api.kanye.rest");
        const text = (await response.json()).quote;
        tweet_url = `https://twitter.com/intent/tweet?text=${encodeURIComponent(
            text + " -https://kanye.rest"
        )}`;
        return text;
    }

    let quote = getQuote();

    function refresh() {
        quote = getQuote();
    }

    function tweet() {
        window.open(tweet_url);
    }
</script>

<main>
    <div class="top">
        <a href="https://api.kanye.rest">https://api.kanye.rest</a>

        <button on:click={tweet}>📢 tweet</button>
        <button on:click={refresh}>🔄 refresh</button>
    </div>

    <div class="quote card">
        {#await quote}
            <p>loading...</p>
        {:then data}
            <p in:fly={{ x: -100, duration: 150 }}>
                "{data}"
            </p>
        {/await}
        <span> - Kanye West</span>
    </div>
</main>

<style>
    main {
        display: flex;
        flex-direction: column;
    }

    .top {
        display: flex;
        padding: 0.75rem 1rem;
    }

    a {
        margin-right: auto;
    }

    button {
        margin-left: 0.5rem;
        border: none;
        outline: none;
        cursor: pointer;
        background-color: transparent;
        font-family: inherit;
        font-size: 0.8rem;
        font-weight: 500;
    }

    .quote {
        position: relative;
    }

    p {
        margin: 0.5rem 0;
    }

    span {
        padding: 6px 8px;
        font-size: 0.8rem;
        font-weight: 400;
        position: absolute;
        bottom: 0;
        right: 0;
        color: var(--sub);
        border-radius: 0 0 10px 0;
    }
</style>
