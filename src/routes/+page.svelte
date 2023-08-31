<script lang="ts">
    import Menu from "$lib/Menu.svelte";
    import MenuToggle from "$lib/MenuToggle.svelte";
    import Tuner from "$lib/Tuner.svelte";

    let width = "400px";
    let height = "calc(100% - 70px)";
    let animationOptions: any = "from-right";
    let top = "70px";
    let left = "0px";
    let showBackground = false;
    let animationSpeed = "0.15";

    $: previewCode = `\n<div class="menu-parent" style="\n    width: ${width};\n    height: ${height};\n    top: ${top};\n    left: ${left};\n    background: ${showBackground ? "hsl(259, 100%, 65%)" : "none"};\n">\n    <Menu\n        animationStyle="${animationOptions}"\n        animationSpeed={${animationSpeed}}\n    >\n        <p>Awesome Menu</p>\n    </Menu>\n</div>`;
</script>

<header>
    <h1>Menu Toggler</h1>
    <MenuToggle />
</header>
<div class="menu-parent" style="
    width: {width};
    height: {height};
    top: {top};
    left: {left};
    background: {showBackground ? "hsla(259, 100%, 65%, 0.5)" : "none"};
">
    <Menu animationStyle={animationOptions} {animationSpeed}>
        <label class="background-check">
            <p>Show purple background</p>
            <input type="checkbox" bind:checked={showBackground}>
        </label>
        <code>
            <pre>{previewCode}</pre>
        </code>
    </Menu>
</div>
<main>
    <Tuner bind:width bind:height bind:animationOptions bind:top bind:left bind:animationSpeed />
</main>

<style>
    header {
        width: 100vw;
        height: 70px;
        background-color: #f3f3f3;
        display: flex;
        align-items: center;
        justify-content: space-between;
        padding: 0 15px;
    }

    header h1 {
        font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
        font-weight: bold;
        font-size: 2rem;
    }

    main {
        width: 100vw;
        height: calc(100vh - 70px);
        height: calc(100dvh - 70px);
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .menu-parent {
        position: fixed;
        /* top: 70px;
        left: 0; */
        /* width: 400px;
        height: calc(100vh - 70px); */
        overflow: hidden;
        z-index: 200;
        pointer-events: none;
    }

    code {
        background-color: black;
        width: 100%;
        height: 100%;
    }

    code pre {
        width: 100%;
        white-space:pre-wrap;
    }

    .background-check {
        display: flex;
        align-items: center;
        justify-content: space-between;
        margin: 0 25px;
    }
</style>