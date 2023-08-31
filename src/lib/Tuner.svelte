<script lang="ts">
    import Input from "./Input.svelte";
    import Selector from "./Selector.svelte";
    type AnimationOptions = "from-right" | "from-left" | "from-bottom" | "from-top" | "opacity-change" | "none";
    export let width: string;
    export let height: string;
    export let animationOptions: AnimationOptions;
    export let top: string;
    export let left: string;
    export let animationSpeed: string;

</script>
<section>
    <Input bind:value={width} label="Width" />
    <br>
    <Input bind:value={height} label="Height" />
    <br>
    <Input bind:value={top} label="Top" />
    <br>
    <Input bind:value={left} label="Left" />
    <br>
    <Input bind:value={animationSpeed} label="Animation speed (seconds)" />
    <br>
    <Selector bind:value={animationOptions} label="Animation style"/>
    <br>
    <!-- <label>
        <p>Show Red Background</p>
        <input type="checkbox" bind:checked={showBackground}>
    </label>
    <code>
        <pre>{code}</pre>
    </code> -->
    <noscript></noscript>
</section>

<style>
    section {
        width: 400px;
        background-color: #ffffff;
        border: 1px solid #dfdfdf;
        border-radius: 10px;
        position: relative;
        padding: 10px 20px;
        box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;
    }

    noscript {
        width: 100%;
        height: 100%;
        background-color: #ffffff;
        position: absolute;
        top: 0;
        left: 0;
    }
</style>