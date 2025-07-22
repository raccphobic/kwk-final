<script>
    let { children } = $props();
</script>

<div class="article-text">
    <p>
        {@render children()}
    </p>
</div>

<style>
    .article-text {
        margin: 50vh auto;
        width: 50%;
        color: rgb(95, 45, 110);
        font-size: 1.8rem;
        padding: 20px;
    }
</style>
