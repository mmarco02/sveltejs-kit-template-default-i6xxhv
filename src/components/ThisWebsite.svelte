<script>
</script>

<div class="section-container">
    <div class="text-container">
        <p>
            test
        </p>
    </div>
</div>

<style>
    .section-container {
        display: flex;
        position: relative;
        text-align: center;
        padding: 2rem;
        background: rgba(255, 255, 255, 0.8);
        border-radius: 8px;
        box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
        margin: 2rem auto;
        max-width: 80%;
        width: 70vw;
        height: 10%;
        top: 190vh;
    }

    .text-container {
        flex: 1;
    }

    p {
        font-size: 1.2em;
        line-height: 1.5;
        font-family: 'Fugaz One', sans-serif;
        margin: 0;
    }

    @media (max-width: 768px) {
        .section-container {
            padding: 1rem;
        }

        p {
            font-size: 1em;
        }
    }
</style>
