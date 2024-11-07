<script>
    import { t, locale, locales } from "../locales/i18n";
</script>

<!-- Language Selector -->
<select class="lang-select" bind:value={$locale}>
    {#each locales as l}
        <option value={l}>{l}</option>
    {/each}
</select>

<style>
    .lang-select {
        z-index: 2000000;
        position: absolute;
        left: 1rem;
        padding: 0.5rem;
        font-size: 1rem;
        background-color: transparent;
        border: none;
        margin: 0;
        width: 5%;
        outline: none;
        border-radius: 20%;
        font-family: inherit;
        cursor: inherit;
        line-height: inherit;
    }

    .lang-select:hover {
        background-color: rgba(0, 95, 254, 0.5);
    }

    @media (max-width: 768px) {
        .lang-select {
            top: 1rem;
            left: 1rem;
        }
    }
</style>
