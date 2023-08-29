<script lang="ts">
    import Menu from "$lib/Menu.svelte";
    import MenuToggle from "$lib/MenuToggle.svelte";
</script>

<header>
    <h1>wow</h1>
    <MenuToggle />
</header>
<div class="menu-parent">
    <Menu>
        <ul>
            <li>Hello</li>
            <li>There</li>
        </ul>
    </Menu>
</div>

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
    .menu-parent {
        position: relative;
    }
</style>