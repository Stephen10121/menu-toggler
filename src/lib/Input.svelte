<script lang="ts">
    export let value: string;
    export let error: string | null = null;
    export let label: string;
    export let placeholder = "";
</script>

<label class="{error ? "error" : ""}">
    <p id="label">{label}</p>
    <div class="border">
        <input bind:value={value} {placeholder} on:keyup={(e) => {
            if(e.currentTarget.value.length > 0) error=null
        }}>
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

    input {
        width: 100%;
        aspect-ratio: 20/1;
        font-family: "Poppins", sans-serif;
        font-size: 1rem; 
        /* font-size: 2rem; */
        font-weight: 700;
        padding: 0;
        border: none;
        outline: none;
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
    input::-webkit-outer-spin-button,
    input::-webkit-inner-spin-button {
        -webkit-appearance: none;
        margin: 0;
    }

    /* Firefox */
    input[type=number] {
        -moz-appearance: textfield;
    }
</style>