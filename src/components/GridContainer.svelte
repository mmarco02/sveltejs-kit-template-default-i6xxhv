<script>
    import { writable } from 'svelte/store';
    import { onMount, onDestroy } from 'svelte';
    import { goto } from "$app/navigation";
    import WorkExperience from "./workexperience.svelte";

    export let buttons = [];
    let expandedTile = writable(null);
    let isClosing = false;

    const dynamicButtons = [
        { key: "test", subClass: "medium-tile", link: null, content: WorkExperience },
    ];

    function expandTile(name, link) {
        if (link) {
            if (link.startsWith('http')) {
                window.open(link, '_blank'); // Open external links in a new tab
            } else {
                goto(link); // Use goto() for internal navigation
            }
        } else {
            expandedTile.set(name);
            document.documentElement.style.overflow = 'hidden';
            isClosing = false;
        }
    }

    function closeTile() {
        isClosing = true;
        document.documentElement.style.overflow = '';
        setTimeout(() => {
            expandedTile.set(null);
        }, 400);
    }

    function handleKeydown(event) {
        if (event.key === "Escape") {
            closeTile();
        }
    }

    onMount(() => {
        if (typeof window !== 'undefined') {
            window.addEventListener('keydown', handleKeydown);
        }
    });

    onDestroy(() => {
        if (typeof window !== 'undefined') {
            window.removeEventListener('keydown', handleKeydown);
        }
    });
</script>

<div class="grid-container">
    {#each buttons as { key, subClass, link, content }}
        <button
    class="grid-tile {subClass}"
    on:click={() => expandTile(key, link)}
    on:keydown={(event) => {
        if (event.key === "Enter" || event.key === " ") {
            expandTile(key, link);
        }
    }}
    aria-label="{key}"
>
    <span>{key}</span>
</button>

    {/each}
</div>


{#if $expandedTile}
    <!-- Overlay container for expanded content -->
    <div class="expanded-overlay {isClosing ? 'closing' : ''}" on:click={closeTile}>
        <div class="expanded-content" on:click|stopPropagation>
            <button class="back-button" on:click={closeTile}>
                &larr;
            </button>
            <h1 class="expanded-title">{$expandedTile}</h1>
            {#each dynamicButtons as { key, content }}
                {#if $expandedTile === key}
                    <svelte:component this={content} />
                {/if}
            {/each}
        </div>
    </div>
{/if}

<style>
    .grid-container {
        position: absolute;
        top: 140vh;
        left: 0;
        right: 0;
        padding: 1rem;
        display: inline-grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 1rem;
        z-index: 1;
        background: none;
        max-width: 100vw;
    }

    .grid-tile {
        display: flex;
        align-items: center;
        justify-content: center;
        background: rgba(255, 255, 255, 0);
        backdrop-filter: blur(12px);
        border: 0.1em solid #005ffe;
        font-size: 1.5em;
        cursor: none;
        border-radius: 8px;
        transition: transform 0.2s, background-color 0.2s;
        position: relative;
        font-family: 'Fugaz One', sans-serif;
    }

    .grid-tile:hover {
        transform: scale(1.02);
        backdrop-filter: blur(0px);
    }

    .expanded-overlay {
        position: fixed;
        top: 0;
        left: 0;
        width: 100vw;
        height: 100vh;
        background: rgba(255, 255, 255, 1);
        backdrop-filter: blur(12px);
        z-index: 1000;
        display: flex;
        flex-direction: column;
        padding: 0;
        box-shadow: 0 0 15px rgba(0, 0, 0, 0.3);
        overflow: hidden;
        animation: expandAnimation 0.6s cubic-bezier(0.25, 1, 0.5, 1) forwards;
    }

    .expanded-overlay.closing {
        animation: shrinkAnimation 0.6s cubic-bezier(0.25, 1, 0.5, 1) forwards;
    }

    .expanded-content {
        width: 100vw;
        height: 100vh;
        overflow-y: auto;
        padding: 2rem;
        box-sizing: border-box;
        position: relative;
    }

    .back-button {
        position: absolute;
        top: 1rem;
        left: 1rem;
        font-size: 2em;
        background: none;
        border: none;
        cursor: pointer;
        color: #005ffe;
    }

    .expanded-title {
        margin: 0;
        font-size: 3em;
        text-align: center;
        font-family: 'Fugaz One', sans-serif;
    }

    @keyframes expandAnimation {
        0% {
            transform: scale(0);
            opacity: 0;
        }
        100% {
            transform: scale(1);
            opacity: 1;
        }
    }

    @keyframes shrinkAnimation {
        0% {
            transform: scale(1);
            opacity: 1;
        }
        100% {
            transform: scale(0);
            opacity: 0;
        }
    }

    .medium-tile { height: 200px; }

    @media (max-width: 768px) {
        .grid-container {
            grid-template-columns: repeat(2, 1fr);
        }
    }

    @media (max-width: 480px) {
        .grid-container {
            grid-template-columns: 1fr;
        }
        .grid-tile { font-size: 1em; }
    }
</style>