<script>
    import { fade, fly } from "svelte/transition";
    import Scroller from "../lib/Scroller.svelte";
    import ObservedArticleText from "../lib/ObservedArticleText.svelte";

    let duckIsVisible = $state(false);

    const options = {
        threshold: [0.85, 0.95],
    };

    const simpleCallback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio >= 0.9) {
                elem.style.backgroundColor = "#fbbdff";
            } else if (entry.intersectionRatio < 0.9) {
                elem.style.backgroundColor = "#fbbdff";
            }
        });
    };

    const showDuckCallback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio >= 0.9) {
                elem.style.backgroundColor = "#fbbdff";
                duckIsVisible = true;
            } else if (entry.intersectionRatio < 0.9) {
                elem.style.backgroundColor = "#fbbdff";
            }
        });
    };

    const removeDuckCallback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio >= 0.9) {
                elem.style.backgroundColor = "#fbbdff";
                duckIsVisible = false;
            } else if (entry.intersectionRatio < 0.9) {
                elem.style.backgroundColor = "#fbbdff";
            }
        });
    };
</script>

<div>
    <Scroller layout="left">
        {#snippet sticky()}
            <div>
                {#if duckIsVisible}
                    <img
                        class="duck-img"
                        src="Degree.png"
                        alt="KWK rubber duck!"
                        in:fly={{ y: 200, duration: 2000 }}
                        out:fade
                    />
                {/if}
                <br />
            </div>
        {/snippet}

        {#snippet scrolly()}

            <ObservedArticleText callback={showDuckCallback} {options}>
                As you can see in this graph, Asians attain the most bachelor's degrees, while Hispanic people have the least bachelor's degrees. 
                <br /><br />
                So yes, it does make sense that Asians would be employed in STEM more, since there's a larger percentage of them. However, Black people have a higher degree attainment
                then hispanic people, yet their employment levels are less. So this disproves the fact that if you have more graduates, it leads to higher employment.
            </ObservedArticleText>

            <ObservedArticleText callback={removeDuckCallback} {options}>
                All our data proves insinuates that no matter the degree or the qualifications, there is still a certain bias when it comes to hiring employees. So, we can come to our own conclusion from our data that degrees don't seem to be enough for certain employers.
            </ObservedArticleText>

        {/snippet}
    </Scroller>
</div>

<style>

    .duck-img {
        margin: 0 auto;
        width: 600px;
        height: auto;
    }

</style>
