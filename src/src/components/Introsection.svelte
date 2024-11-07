<script>
    import '@fontsource/fugaz-one';
    import { t, locale, locales } from "../locales/i18n.js"
</script>

<div class="intro-section">
    <div class="image-container">
        <img src="/removed_BG_Portrait.png" alt="Portrait">
    </div>
    <div class="text-container">
        <p>
            {@html $t("introsection.text")}
        </p>
    </div>
</div>

<style>
    .intro-section {
        display: flex;
        position: relative;
        align-items: center;
        justify-content: space-between;
        padding: 2rem;
        background: rgba(255, 255, 255, 0.8);
        border-radius: 8px;
        box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
        margin: 2rem auto;
        max-width: 70vw;
        width: 70vw;
        height: 24vh;
        top: 101vh;
        text-align: center;
    }

    .image-container {
        flex: 0 0 auto;
        width: 12rem;
        height: 12rem;
        border-radius: 50%;
        overflow: hidden;
        margin-left: 10%;
    }

    img {
        width: 100%;
        height: 130%;
        margin-top: 0;
        object-fit: cover;
        display: block;
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
        .intro-section {
            flex-direction: column;
            align-items: center;
            text-align: center;
        }

        .image-container {
            margin: 0 0 1rem 0;
            width: 8rem;
            height: 8rem;
        }
    }
</style>
