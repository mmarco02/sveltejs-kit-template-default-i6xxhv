<script>
    import { onMount } from "svelte";
    import { gsap } from "gsap";
    import NameContainer from '../components/NameContainer.svelte';
    import GridContainer from '../components/GridContainer.svelte';
    import WorkExperience from "../components/Tiles/WorkExperience.svelte";
</script>

<style>
    :root {
        overflow-x: hidden;
    }
</style>


<div class="content-container">
    <NameContainer name="Marco"/>
    <GridContainer/>
</div>