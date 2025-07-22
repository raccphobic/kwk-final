<script>
  import Scroller from "../lib/Scroller.svelte";
  import ArticleText from "../lib/ArticleText.svelte";
  
  const quotes = [
    "When you're at the intersection of race and gender, you're not just fighting one battle — you're fighting both at once.",
    "We were told if we worked twice as hard, we'd get half as far. Turns out that wasn't a metaphor.",
    "You can't fix inequality just by telling people to get educated. The system has to be ready to let them in.",
  ];
</script>

<div>
  <Scroller layout="right">
    {#snippet sticky()}
      <div class="quote-container">
        <div class="quote-box">
          {#each quotes as quote}
            <blockquote>
              {quote}
            </blockquote>
          {/each}
        </div>
      </div>
    {/snippet}

    {#snippet scrolly()}
      <ArticleText>
        <strong>Throughout History</strong>
      </ArticleText>
      
      <ArticleText>
        The struggle of black people in the industry has been very clear
      </ArticleText>
      
      <ArticleText>
        To the point where it's demotivating, and as a black person it makes you think,
      </ArticleText>
      
      <ArticleText>
        <strong>What's the point?</strong>
      </ArticleText>
    {/snippet}
  </Scroller>
  
</div>

<style>
  .quote-box {
    display: flex;
    flex-direction: column;
    gap: 2rem;
  }
  
  blockquote {
    font-family: 'Georgia', serif;
    font-size: 1.5rem;
    line-height: 1.6;
    color: #333;
    padding: 2rem;
    margin: 0;
    border-left: 4px solid rgb(113, 76, 126);
    background: #f9f9f9;
    position: relative;
  }

  blockquote::before {
    content: '"';
    font-size: 4rem;
    color: rgb(209, 184, 217);
    opacity: 0.2;
    position: absolute;
    left: 10px;
    top: -10px;
  }

  blockquote::after {
    content: '"';
    font-size: 4rem;
    color: rgb(209, 184, 217);
    opacity: 0.2;
    position: absolute;
    right: 10px;
    bottom: -30px;
  }
</style>