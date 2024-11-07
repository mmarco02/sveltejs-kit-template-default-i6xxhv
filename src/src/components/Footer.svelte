<script>
    import '@fontsource/fugaz-one';
    import LanguageSelect from "./LanguageSelect.svelte";
</script>

<style>
    .footer {
        display: flex;
        position: absolute;
        align-items: center;
        justify-content: space-between;
        padding: 1rem 2rem;
        background: rgba(255, 255, 255, 0.8);
        border-top: 0.1em solid #005ffe;
        font-family: 'Fugaz One', sans-serif;
        font-size: 1em;
        box-shadow: 0 -4px 10px rgba(0, 0, 0, 0.1);
        top: 250vh;
        left: 0;
        width: 100vw;
        z-index: 1;
    }

    .footer-content {
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: center;
        width: 100vw;
    }

    .footer-links {
        display: flex;
        gap: 1.5rem;
        margin-top: 0.5rem;
    }

    .footer-links a {
        color: #005ffe;
        text-decoration: none;
        transition: color 0.2s;
    }

    .footer-links a:hover {
        color: #002a8e;
    }

    .footer-note {
        margin-top: 0.5rem;
        font-size: 0.9em;
        color: #333;
    }

    @media (max-width: 768px) {
        .footer {
            flex-direction: column;
            padding: 1rem;
        }

        .footer-content {
            text-align: center;
        }

        .footer-links {
            flex-direction: column;
            gap: 0.5rem;
        }
    }
</style>

<div class="footer">
    <div class="footer-content">
        <div class="footer-links">
            <a href="https://github.com/mmarco02" target="_blank">GitHub</a>
            <a href="https://www.linkedin.com/in/marco-molnár-90bba8333/" target="_blank">LinkedIn</a>
            <a href="/about" on:click|preventDefault>About Me</a>
        </div>
        <div class="footer-note">
            © {new Date().getFullYear()} Marco Molnár. All rights reserved.
        </div>
    </div>

    <LanguageSelect/>
</div>
