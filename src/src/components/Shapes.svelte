<div class="shapes" style="background: linear-gradient(180deg, {maincolor} 50%, white 50%);">
    <div class="shape shape-1" style="background: {color1}"></div>
    <div class="shape shape-2" style="background: {color2}"></div>
    <div class="shape shape-3" style="background: {color3}"></div>
</div>

<script>
    export let color1 = '#005ffe';
    export let color2 = '#ffe5e3';
    export let color3 = '#ffcc57';
    export let maincolor = '#005ffe';

</script>

<style>
    .shapes {
        position: absolute;
        top: 0;
        left: 0;
        width: 100vw;
        height: 200vh;
        pointer-events: none;
        z-index: 0;
    }

    .shape {
        position: fixed;
        border-radius: 50%;
    }

    .shape-1 { width: 650px; height: 650px; margin: -325px 0 0 -325px; }
    .shape-2 { width: 440px; height: 440px; margin: -220px 0 0 -220px; }
    .shape-3 { width: 270px; height: 270px; margin: -135px 0 0 -135px; }
</style>
