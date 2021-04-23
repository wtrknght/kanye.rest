<script>
    // https://raw.githubusercontent.com/ajzbc/kanye.rest/master/quotes.json

    let quotes;
    let toggle = false;

    fetch(`https://raw.githubusercontent.com/ajzbc/kanye.rest/master/quotes.json`)
        .then((r) => r.json())
        .then((data) => {
            quotes = data.sort(() => Math.random() - 0.5);
        });
</script>

<main>
    <div class="card">
        <div class="toggle">
            <button on:click={() => (toggle = !toggle)}>
                {toggle ? "⬇️" : "➡️"} Quotes List
            </button>
            {#if toggle == true}
                <a href="https://github.com/ajzbc/kanye.rest/blob/master/quotes.json">source</a>
            {/if}
        </div>
        {#if toggle == true}
            {#if quotes}
                <ul>
                    {#each quotes as quote, i}
                        <li>{quote}</li>
                    {/each}
                </ul>
            {/if}
        {/if}
    </div>
</main>

<style>
    div {
        display: flex;
    }

    .card {
        flex-direction: column;
    }

    button {
        padding: 0;
        border: none;
        outline: none;
        cursor: pointer;
        background-color: transparent;
        text-align: left;
        font-family: inherit;
        font-size: 1rem;
        font-weight: 500;
        width: 100%;
    }

    ul {
        margin: 0;
        margin-top: 1rem;
        padding: 0;

        border-top: 2px solid #999999;

        list-style-type: none;

        overflow-y: auto;
        max-height: 325px;

        -ms-overflow-style: none; /* IE and Edge */
        scrollbar-width: none; /* Firefox */
    }

    ul::-webkit-scrollbar {
        display: none; /* Safari and Chrome */
    }

    li {
        padding: 0.5rem;
        border-bottom: 1px solid #bbbbbb;
        font-size: 0.9rem;
        font-weight: 400;
    }

    li:last-child {
        border: none;
    }
</style>
