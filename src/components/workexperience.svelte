<script>
    import { onMount } from 'svelte';
    import gsap from 'gsap';
    import {ScrollTrigger} from "gsap/dist/ScrollTrigger";

    onMount(() => {
        gsap.registerPlugin(ScrollTrigger);

        gsap.from(".work-tile", {
            opacity: 0,
            x: -50,
            duration: 1,
            stagger: 0.3,
            scrollTrigger: {
                trigger: ".work-experience",
                toggleActions: "restart pause none none",
                start: "top 80%",
                end: "bottom 20%",
                scrub: 2,
            }
        });
    });


</script>

<div class="work-experience">
    <div class="work-tile">
        <h2>a</h2>
        <ul>
            <li>.</li>
            <li>.</li>
            <li>.</li>
            <li>.</li>
        </ul>
    </div>

    <div class="work-tile">
        <h2>b</h2>
        <ul>
            <li>.</li>
            <li>.</li>
            <li>.</li>
        </ul>
    </div>

    <div class="work-tile">
        <h2>c</h2>
        <ul>
            <li>.</li>
            <li>.</li>
        </ul>
    </div>
</div>

<style>
    .work-experience {
        height: 100vh;
    }

    .work-tile {
        margin: 10rem;
    }

    h2 {

    }

    ul {

    }

    li {

    }
</style>