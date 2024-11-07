<script>
    import { onMount } from 'svelte';
    import gsap from 'gsap';
    import { writable } from 'svelte/store';
    import { onDestroy } from 'svelte';

    let isAboutMeVisible = writable(false);  // Track visibility of the AboutMe content

    // Trigger the animation when the AboutMe component is displayed
    onMount(() => {
        // When the component is mounted and AboutMe becomes visible
        isAboutMeVisible.set(true);
    });

    // When AboutMe content is visible, trigger the animation
    $: if ($isAboutMeVisible) {
        gsap.from(".about-me p", {
            opacity: 0,       // Start with opacity 0
            y: 50,            // Start from below the viewport
            duration: 1,      // Animation duration
            ease: "power2.out" // Ease for smoothness
        });
    }
</script>

<div class="about-me">
    <p>
        {$t("aboutme.text1")}
        <br><br>
        {$t("aboutme.text2")}
        <br><br>
        {$t("aboutme.text3")}
        <br><br>
        {$t("aboutme.text4")}
        <br><br>
        {$t("aboutme.text5")}
    </p>
</div>

<style>
    * {
        font-family: 'Fugaz One', sans-serif;
    }

    .about-me {
        max-width: 600px;
        margin: 0 auto;
        padding: 1rem;
    }

    h1 {
        font-size: 2rem;
        text-align: center;
        margin-bottom: 1rem;
    }

    p {
        font-size: 1rem;
        line-height: 1.6;
    }
</style>
