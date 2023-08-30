<script lang="ts">
    import Menu from "$lib/Menu.svelte";
    import MenuToggle from "$lib/MenuToggle.svelte";
</script>

<!-- <noscript> -->
    <header>
        <h1>wow</h1>
        <MenuToggle />
    </header>
    <div class="menu-parent">
        <Menu animationStyle="opacity-change">
            <ul>
                <li>Hello</li>
                <li>There</li>
            </ul>
        </Menu>
    </div>
<!-- </noscript>
<section>
    <p>Disable Javascript</p>
</section> -->

<style>
    section {
        width: 100%;
        height: 100vh;
        display: flex;
        align-items: center;
        justify-content: center;
    }
    section p {
        font-family: sans-serif;
        font-weight: bold;
        font-size: 2rem;
    }
    noscript {
        width: 100vw;
        height: 100vh;
    }

    header {
        width: 100vw;
        height: 70px;
        background-color: #f3f3f3;
        display: flex;
        align-items: center;
        justify-content: space-between;
        padding: 0 15px;
    }
    .menu-parent {
        position: relative;
        width: 400px;
        height: calc(100vh - 70px);
        overflow: hidden;
    }
</style>