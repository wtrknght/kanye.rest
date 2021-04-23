<script>
    import Quote from "./Quote.svelte";
    import Ad from "./Ad.svelte";
    import List from "./List.svelte";
</script>

<main>
    <div class="container center">
        <h2><a href="./">🌊 kanye.rest</a></h2>
        <span>A free REST API for random Kanye West quotes (Kanye as a Service)</span>
    </div>

    <div class="container">
        <Quote />
    </div>

    <div class="container ad">
        <Ad />
    </div>

    <div class="container">
        <List />
    </div>

    <div class="container center">
        <p>
            👋
            <a href="https://twitter.com/ajzbc">@ajzbc</a>
        </p>
        <p>
            <a href="https://github.com/ajzbc/kanye.rest">
                <img
                    src="https://img.shields.io/github/stars/ajzbc/kanye.rest?style=social"
                    alt="Github Link"
                />
            </a>
        </p>
    </div>
</main>

<style>
    .container {
        margin-bottom: 2rem;
    }

    .center {
        text-align: center;
    }

    h2 {
        margin: 0.8rem 0;
    }

    h2 a,
    h2 a:hover {
        color: var(--main);
        text-decoration: none;
    }

    span {
        color: var(--sub);
        font-size: 0.8rem;
        font-weight: 400;
    }

    p {
        margin: 0.75rem 0;
    }
</style>
