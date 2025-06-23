<script>
    // @ts-nocheck

    import { onMount, onDestroy, createEventDispatcher } from "svelte";
    import { tick } from "svelte";

    export let gap = 10;
    export let maxColumnWidth = 250;
    export let hover = false;
    export let loading = 'lazy';

    const dispatch = createEventDispatcher();

    let slotHolder = null;
    let columns = [];
    let galleryWidth = 0;
    let columnCount = 0;

    $: columnCount = parseInt(galleryWidth / maxColumnWidth) || 1;
    $: columnCount && Draw();
    $: galleryStyle = `grid-template-columns: repeat(${columnCount}, 1fr); --gap: ${gap}px`;

    onMount(Draw);
    onDestroy(Draw);

    function HandleClick(e) {
        dispatch("click", {
            tag: e.target.tagName,
            src: e.target.src || e.target.currentSrc,
            alt: e.target.alt || '',
            class: e.target.className
        });
    }

    async function Draw() {
        await tick();

        if (!slotHolder) return;

        const mediaElements = Array.from(slotHolder.childNodes).filter(
            (el) =>
                el.tagName === "IMG" ||
                (el.tagName === "VIDEO" && el.src.endsWith(".webm"))
        );

        columns = [];

        for (let i = 0; i < mediaElements.length; i++) {
            const el = mediaElements[i];
            const idx = i % columnCount;

            const mediaData = {
                tag: el.tagName,
                src: el.src,
                alt: el.alt || '',
                class: el.className,
                controls: el.controls || true,
                autoplay: el.autoplay || false,
                loop: el.loop || false,
                muted: el.muted || false
            };

            columns[idx] = [...(columns[idx] || []), mediaData];
        }
    }
    </script>

    <div id="slotHolder" bind:this={slotHolder}>
        <slot />
    </div>

    {#if columns}
        <div id="gallery" bind:clientWidth={galleryWidth} style={galleryStyle}>
            {#each columns as column}
                <div class="column">
                    {#each column as media}
                        {#if media.tag === 'IMG'}
                            <img
                                src={media.src}
                                alt={media.alt}
                                on:click={HandleClick}
                                on:keydown={HandleClick}
                                class="{hover ? 'img-hover' : ''} {media.class}"
                                loading={loading}
                            />
                        {:else if media.tag === 'VIDEO'}
                            <video
                                src={media.src}
                                on:click={HandleClick}
                                on:keydown={HandleClick}
                                class="{hover ? 'img-hover' : ''} {media.class}"
                                controls
                                autoplay={media.autoplay}
                                loop={media.loop}
                                muted={media.muted}
                            />
                        {/if}
                    {/each}
                </div>
            {/each}
        </div>
    {/if}

    <style>
    #slotHolder {
        display: none;
    }
    #gallery {
        width: 100%;
        display: grid;
        gap: var(--gap);
    }
    #gallery .column {
        display: flex;
        flex-direction: column;
    }
    #gallery .column * {
        width: 100%;
        margin-top: var(--gap);
    }
    #gallery .column *:nth-child(1) {
        margin-top: 0;
    }
    .img-hover {
        opacity: 0.9;
        transition: all 0.2s;
    }
    .img-hover:hover {
        opacity: 1;
        transform: scale(1.05);
    }
    </style>
