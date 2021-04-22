<script>
    import Quote from "./Quote.svelte";
</script>

<main>
    <div class="wrapper">
        <div class="container header">
            <h2><a href="./">🌊 kanye.rest</a></h2>
            <span>A free REST API for random Kanye West quotes (Kanye as a Service)</span>
        </div>

        <div class="container">
            <Quote />
        </div>

        <div class="container ad">
            <script
                async
                type="text/javascript"
                src="https://cdn.carbonads.com/carbon.js?serve=CE7D5K7M&placement=kanyerest"
                id="_carbonads_js">
            </script>
        </div>

        <!-- test to see if this shows up -->
        <div class="container ad">
            <blockquote class="twitter-tweet">
                <p lang="en" dir="ltr">
                    Bought another domain... I need to finish projects first. 🤦‍♂️
                </p>
                &mdash; Andrew Jazbec (@ajzbc)<a
                    href="https://twitter.com/ajzbc/status/1175865185514377216?ref_src=twsrc%5Etfw"
                    >September 22, 2019</a
                >
            </blockquote>
            <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
        </div>

        <div class="container footer">
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
    </div>
</main>

<style>
    .wrapper {
        margin: 0 auto;
        max-width: 550px;
    }

    .container {
        margin-bottom: 2rem;
    }

    .header {
        text-align: center;
    }

    .ad {
        min-height: 100px;
    }

    .footer {
        text-align: center;
    }

    h2 {
        margin: 0.8rem 0;
    }

    h2 a,
    h2 a:hover {
        color: var(--main-text);
        text-decoration: none;
    }

    span {
        color: var(--sub-text);
        font-size: 0.8rem;
    }

    p {
        margin: 0.75rem 0;
    }
</style>
