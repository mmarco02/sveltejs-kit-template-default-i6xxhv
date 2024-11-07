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
        <h2>Praktikum, Agrana Pischelsdorf (2022)</h2>
        <ul>
            <li>Konfiguration von AccessPoints</li>
            <li>1st und 2nd Level IT Support</li>
            <li>Reparatur, Reinigung und Bearbeitung von elektronischen Geräten</li>
            <li>Instandhaltung von Sicherheitsstandards und Software auf Arbeitsgeräten</li>
        </ul>
    </div>

    <div class="work-tile">
        <h2>Praktikum, Exclusive Networks (2023)</h2>
        <ul>
            <li>Aufbau und Arbeit in Laborumgebungen mit Hardware- und Software-Komponenten.</li>
            <li>Hardware-Komponente auf diverse Funktionen testen</li>
            <li>Troubleshooting von Netzwerk-Komponenten</li>
        </ul>
    </div>

    <div class="work-tile">
        <h2>Nachhilfelehrer bei Schülerhilfe (2022-2024)</h2>
        <ul>
            <li>Deutsch, Englisch, Mathematik, Betriebswirtschaft</li>
            <li>Umgang mit Kindern verschiedenen Alters</li>
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
