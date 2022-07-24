<script lang="ts">
    import {fade} from "svelte/transition";
    import {useNavigate} from "svelte-navigator";
    import {bounceIn} from 'svelte/easing';
    import {onMount} from "svelte";

    const navigate = useNavigate();
    let visible = false;
    export let delay;
    export let title;
    onMount(() => visible = true);
</script>
{#if visible}
<div in:fade="{{delay: delay * 2, duration: 500, x:1000, y: 1000, opacity: 0.5}}" class="product-container"
     on:click={() => navigate("product")}>
    <h2>{title}</h2>
    <div class="img"></div>
</div>
{/if}
<style>
    .product-container {
        background-color: whitesmoke;
        border-radius: 2rem;
        box-shadow: 0 2px 12px 2px rgba(0, 0, 0, 0.2);
        height: 15rem;
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    h2 {
        color: dimgray;
        outline: none;
    }

    .img {
        background-image: url("../assets/tonic.png");
        width: 100%;
        flex: 1;
        border-bottom-left-radius: 2rem;
        border-bottom-right-radius: 2rem;
        background-size: cover;
        position: relative;
        overflow: hidden;
        background-position: top -5rem center;
    }
</style>
