<script>
    let { title, subtitle } = $props();
</script>

<div class="title-card">
    <div class="content">
        <h1>{title}</h1>
        <p>{subtitle}</p>
    </div>
</div>

<style>
    .title-card {
        background-color: rgb(209, 184, 217);
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        text-align: center;
        padding: 2rem;
        box-sizing: border-box;
        font-family: "Inter", sans-serif;
    }

    .content {
        max-width: 700px;
        background-color: rgb(209, 184, 217);
        padding: 2rem;
        border-radius: 2rem;
    }

    h1 {
        font-size: 3rem;
        margin: 0;
        color: rgb(95, 45, 110);
        text-shadow: 1px 1px 0 rgb(209, 184, 217);
    }

    p {
        font-size: 1.3rem;
        color: #000000;
        margin-top: 1rem;
    }

    @media (max-width: 600px) {
        h1 {
            font-size: 2.2rem;
        }

        p {
            font-size: 1.1rem;
        }
    }
</style>
