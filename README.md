# Menu Toggler
If you want an amazing looking menu and have it work without javascript, this library is perfect for you. This is a toggle menu that works without Javascript by using css checkboxes. HTML/CSS can be really powerfull and Javascript isn't always neccessary. By utilizing the capabilities of css and html, I created a menu/menu toggler that doesn't use a single line of Javascript.
## Usage
Menu-Toggler gives 2 components. A menu toggle button and the menu itself. You can put the components anywhere in the DOM. It's even possible to place the components in different svelte files.

```html
<header>
    <h1>wow</h1>
    <MenuToggle /> <!-- This component can be anywhere in the DOM  -->
</header>
<div class="menu-parent">
    <Menu animationStyle="from-right"> <!-- This component can also be anywhere in the DOM  -->
        <ul>
            <li>Hello</li>
            <li>There</li>
        </ul>
    </Menu>
</div>
```
As you can see, the menu is wrapped in a parent div with a classname called menu-parent. You can customise the width, height, position of this element, and thats where the menu will appear. The menu uses the position: absolute attribute, so make sure that the menu-parent has a position of relative or absolute or fixed.
```html
<div class="menu-parent">
    <Menu animationStyle="from-right">menu</Menu>
</div>
<style>
    .menu-parent {
        position: relative;
        width: 400px;
        height: 600px;
    }
</style>
```
## Caution
menu-toggler uses the css :has() attribute, so some browsers (firefox) may not support it.

<a href="https://menutoggler.stephengruzin.dev">Example Page.</a> Don't forget to disable Javascript.