<script>
    import '@fontsource/fugaz-one';
    export let name;
</script>

<div class="name-container">
    <span id="name"> {name}</span>
</div>

<style>
    .name-container {
        top: 0;
        left: 0;
        position: absolute;
        display: flex;
        justify-content: center; /* Center horizontally */
        align-items: center;    /* Center vertically */
        height: 100vh;
        width: 100vw;
        background: #fff;
        mix-blend-mode: screen;
        z-index: 2;
        text-align: center; /* Ensure text alignment is center */
    }

    #name {
        font-size: 15em;
        color: #000;
        font-family: 'Fugaz One', sans-serif;
        white-space: nowrap; /* Prevent text wrapping on larger screens */
    }

    @media (max-width: 1200px) {
        #name {
            font-size: 7em;
        }
    }

    @media (max-width: 768px) {
        #name {
            font-size: 5em;
        }
    }

    @media (max-width: 480px) {
        #name {
            font-size: 5em;
            white-space: normal;
        }
    }
</style>
