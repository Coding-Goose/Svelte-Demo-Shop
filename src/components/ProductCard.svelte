<script lang="ts">
    import {fade} from "svelte/transition";
    import StarsContainer from "./StarsContainer.svelte";
    import {onMount} from "svelte";
    import {warenkorb} from "../stores";

    let visible;
    onMount(() => visible = true);

    function onInDenWarenkorb() {
        warenkorb.update(arr => [...arr, {
            lorem: "ipsum"
        }])
    }
</script>

<section>
    <div class="product-image"></div>
    <div class="product-content">
        <div>
            {#if visible}
                <h2 in:fade={500}>Purple Tonic Water</h2>
            {/if}
            <div class="price-container">
                <span class="price">9,99 $</span>
                <StarsContainer/>
            </div>
            <p>Klasse Tonic Water. Schmeckt supi. Kann man gut mit Vodka mischen. Lorem ipsum dolor sit amet,
                consectetur adipisicing elit. A harum ipsam iure omnis qui quis, quos ullam voluptatum! Ab,
                doloribus. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ad animi aut, id magnam maiores nam
                non placeat recusandae rerum sunt.</p>
        </div>
        <button on:click={onInDenWarenkorb}>
            IN DEN WARENKORB
        </button>
    </div>
</section>

<style>
    .price-container {
        display: flex;
        justify-content: space-between;
    }

    button {
        padding: 1rem;
        background-color: #61B68C;
        color: whitesmoke;
        font-size: 1.5rem;
        border: none;
        border-radius: 2rem;
        font-weight: bold;
        box-shadow: 0 2px 12px 2px rgba(0, 0, 0, 0.2);
        cursor: pointer;
    }

    h2 {
        font-weight: bold;
        font-size: 2.5rem;
        outline: none;
    }

    .price {
        font-size: 2rem;
        font-weight: 100;
    }

    .product-content {
        padding: 1rem;
        width: 50%;
        display: flex;
        flex-direction: column;
    }

    .product-content > div {
        flex: 1;
    }

    section {
        width: 100%;
        height: 40rem;
        background: whitesmoke;
        margin-top: 2rem;
        border-radius: 2rem;
        color: dimgray;
        box-shadow: 0 2px 12px 2px rgba(0, 0, 0, 0.2);
        display: flex;
    }

    .product-image {
        background-image: url("../assets/tonic.png");
        width: 50%;
        height: 100%;
        border-bottom-left-radius: 2rem;
        border-top-left-radius: 2rem;
        box-shadow: 0 2px 12px 2px rgba(0, 0, 0, 0.2);
        background-size: cover;
        padding: 1rem;
    }
</style>
