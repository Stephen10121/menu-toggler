<script lang="ts">
    type AnimationOptions = "slide-right" | "slide-left" | "slide-bottom" | "slide-top" | "opacity-change" | "none";
    export let animationStyle: AnimationOptions = "none";
    export let animationSpeed = 0.15;
</script>

<div id="options" class="{animationStyle}" style="--transition-speed: {animationSpeed}s;">
    <slot />
</div>

<style>
    #options {
        position: absolute;
        width: 100%;
        height: 100%;
        background-color: #dfdfdf;
        top: 0;
        left: 0;
        --transition-speed: 0.15s;
    }

    #options.none,
    #options.opacity-change {opacity: 0}
    #options.slide-right,
    #options.slide-bottom,
    #options.slide-top,
    #options.slide-left {transition: transform var(--transition-speed) linear}
    #options.slide-right {transform: translateX(-100%)}
    #options.slide-left {transform: translateX(100%)}
    #options.slide-bottom {transform: translateY(100%)}
    #options.slide-top {transform: translateY(-100%)}
    #options.opacity-change {transition: opacity var(--transition-speed) linear}

    :global(body:has(#menu:checked) #options.slide-bottom),
    :global(body:has(#menu:checked) #options.slide-top) {
        transform: translateY(0);
    }
    :global(body:has(#menu:checked) #options.slide-left),
    :global(body:has(#menu:checked) #options.slide-right) {
        transform: translateX(0);
    }
    
    :global(body:has(#menu:checked) #options.opacity-change),
    :global(body:has(#menu:checked) #options.none) {
        opacity: 1;
    }
</style>