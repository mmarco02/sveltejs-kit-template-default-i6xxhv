<script>
    import { onMount } from "svelte";
    import { gsap } from "gsap";
    import GridContainer from '../components/GridContainer.svelte'
    import { onNavigate } from '$app/navigation';
</script>

<style>
    :root {
        cursor: none;
        overflow-x: hidden;
    }
</style>


<div class="content-container">
    <GridContainer/>
</div>