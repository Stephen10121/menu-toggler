<script lang="ts">
    export let value: string;
    export let error: string | null = null;
    export let label: string;
</script>

<label class="{error ? "error" : ""}">
    <p id="label">{label}</p>
    <div class="border">
        <select name="animationStyle" id="animationStyle-select" bind:value>
            <option value="none">No Animation</option>
            <option value="from-right">From Right</option>
            <option value="from-left">From Left</option>
            <option value="from-bottom">From Bottom</option>
            <option value="from-top">From Top</option>
            <option value="opacity-change">Opacity Change</option>
        </select>
    </div>
    {#if error}
        <p id="error">{error}</p>
    {/if}
</label>

<style>
    label {
        display: flex;
        flex-direction: column;
        gap: 5px;
        position: relative;
        background-color: #ffffff;
    }
    #label {
        font-family: "Poppins";
        font-size: 0.9rem;
        letter-spacing: 2px;
        color: hsl(0, 1%, 44%);
        text-transform: uppercase;
        transition: color 0.15s linear;
    }

    .error #label {
        color: hsl(0, 100%, 67%);
    }

    .error .border {
        border: 1px solid hsl(0, 100%, 67%);
    }

    #error {
        font-family: "Poppins";
        font-size: 0.9rem;
        font-weight: 400;
        font-style: italic;
        color: hsl(0, 100%, 67%);
        position: absolute;
        bottom: -25px;
        left: 0;
    }

    select {
        width: 100%;
        aspect-ratio: 20/1;
        font-family: "Poppins", sans-serif;
        font-size: 1rem; 
        /* font-size: 2rem; */
        font-weight: 700;
        padding: 0;
        border: none;
        outline: none;
        background-color: #ffffff;
        caret-color: hsl(259, 100%, 65%);
    }

    .border:has(input:focus) {
        border: 1px solid hsl(259, 100%, 65%);
    }

    .border {
        border: 1px solid hsl(0, 0%, 86%);
        padding: 10px 20px;
        border-radius: 5px;
        transition: border 0.15s linear;
    }

    /* Chrome, Safari, Edge, Opera */
    select::-webkit-outer-spin-button,
    select::-webkit-inner-spin-button {
        -webkit-appearance: none;
        margin: 0;
    }
</style>