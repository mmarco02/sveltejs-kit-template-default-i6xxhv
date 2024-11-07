<script>
    import { onMount } from "svelte";
    import { gsap } from "gsap";
    import NameContainer from '../components/NameContainer.svelte';
    import Shapes from '../components/Shapes.svelte';
    import CustomCursor from '../components/CustomCursor.svelte';
    import GridContainer from '../components/GridContainer.svelte';
    import Introsection from "../components/Introsection.svelte";
    import { onNavigate } from '$app/navigation';
    import AboutMe from "../components/Tiles/AboutMe.svelte";
    import ThisWebsite from "../components/ThisWebsite.svelte";
    import WorkExperience from "../components/Tiles/WorkExperience.svelte";
    import Education from "../components/Tiles/Education.svelte";
    import Skills from "../components/Tiles/Skills.svelte";
    import Footer from "../components/Footer.svelte";

    let cursorX = 0, cursorY = 0;

    const handleMouseMove = (e) => {
        cursorX = e.clientX;
        cursorY = e.clientY;
        gsap.to(".shape", { x: cursorX, y: cursorY, stagger: -0.1 });
    };

    onMount(() => {
        window.addEventListener("mousemove", handleMouseMove);
        return () => {
            window.removeEventListener("mousemove", handleMouseMove);
        };
    });
</script>

<style>
    :root {
        cursor: none;
        overflow-x: hidden;
    }
</style>


<div class="content-container">
    <NameContainer name="Marco Molnár"/>
    <Shapes/>
    <CustomCursor {cursorX} {cursorY}/>
    <Introsection/>
    <GridContainer/>
    <ThisWebsite/>
    <Footer/>
</div>