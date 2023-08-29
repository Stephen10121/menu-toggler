<script lang="ts">
    export let showAnimation = "slide-right";
</script>

<div id="options" class="{showAnimation}">
    <slot />
</div>

<style>
    #options.slide-right {
        position: absolute;
        width: 200px;
        height: 400px;
        background-color: #dfdfdf;
        top: 0;
        left: 0;
        transform: translateX(-100%);
        transition: transform 0.15s linear;
    }
    :global(body:has(#menu:checked) #options.slide-right) {
        transform: translateX(0);
    }
</style>