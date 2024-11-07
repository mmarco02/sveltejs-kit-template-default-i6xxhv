<script>
    export let cursorX = 0;
    export let cursorY = 0;
    export let color = '#005ffe'
</script>

<div class="cursor" style="background: {color}; transform: translate(calc({cursorX}px - 100%), calc({cursorY}px - 200%));"></div>

<style>
    .cursor {
        width: 1rem;
        height: 1rem;
        border-radius: 50%;
        position: fixed;
        pointer-events: none;
        z-index: 10000;
    }
</style>
