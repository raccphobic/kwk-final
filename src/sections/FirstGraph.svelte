<script>
    import * as Highcharts from "highcharts";
    import "highcharts/modules/exporting";
    import { Chart } from "@highcharts/svelte";
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";

</script>

<div>
    <Scroller layout="left">
        {#snippet sticky()}
      <div class="image-container">
        <img 
          src="Graph.png"
          alt="STEM employment disparities by race and gender" 
          class="content-image"
        >
        
        <div class="image-caption">
          <p>Representing STEM employments seperated by gender and race 2019-2021</p>
        </div>
      </div>
        {/snippet}

        {#snippet scrolly()}
            <ArticleText>
                We can deduct from the graphs that black and hispanic graduates tend to not work in STEM, despite graduating with a STEM degree. This is very different from their white and asian peers, shown by the difference in male employment.
            </ArticleText>

            <ArticleText>
                If we look carefully at the difference between 2019 and 2021 employments in the Black graduates graph, we'll notice that they're the only one of their peers to have either gender go down a whopping 5%.
            </ArticleText>

            <ArticleText>
                This creates a massive gap, around 20%, between Black Male employment and Black Female employment. This means that Black women find it hard to find jobs in STEM due to two things.
            </ArticleText>

            <ArticleText>
                <strong>
                    Their race, and their gender. 
                </strong>
            </ArticleText>
            <ArticleText>Despite having the same STEM degree and qualifications as all their peers, regardless of race or gender. They have the lowest employment rate.</ArticleText>
        {/snippet}
    </Scroller>
</div>

<style>
   .image-container {
    width: 90%;
    margin: 0 auto;
    text-align: center;
    min-height: 400px;
  }
  
  .content-image {
    max-width: 100%;
    max-height: 70vh;
    width: auto;
    height: auto;
    border-radius: 8px;
    box-shadow: 0 4px 12px rgba(0,0,0,0.15);
    display: block;
    margin: 0 auto;
    border: 2px solid #007052;
  }

</style>
