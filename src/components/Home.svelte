<script lang="ts">

    import {useNavigate} from "svelte-navigator";
    import ProductContainer from "./ProductContainer.svelte";

    let products = [
        {
            title: "Purple Tonic Water 1",
            delay: 10
        },
        {
            title: "Purple Tonic Water 2",
            delay: 40
        },
        {
            title: "Purple Tonic Water 3",
            delay: 70
        },
        {
            title: "Purple Tonic Water 4",
            delay: 100
        },
        {
            title: "Purple Tonic Water 5",
            delay: 130
        },
        {
            title: "Purple Tonic Water 6",
            delay: 160
        },
        {
            title: "Purple Tonic Water 7",
            delay: 190
        },
        {
            title: "Purple Tonic Water 8",
            delay: 220
        },
        {
            title: "Purple Tonic Water 9",
            delay: 250
        },
    ];
</script>

<main>
    {#each products as product}
    <ProductContainer delay={product.delay} title={product.title}/>
        {/each}
</main>

<style>
    main {
        margin-top: 2rem;
        display: grid;
        grid-template-columns: auto auto auto;
        grid-template-rows: auto auto auto;
        gap: 1rem;
        grid-template-areas:
    ". . ."
    ". . ."
    ". . .";
    }
</style>
