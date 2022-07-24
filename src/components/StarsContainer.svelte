<script>
    import Star from "./Star.svelte";

    let visible = false;
</script>

<div class="star-container">
    <Star delay={10}></Star>
    <Star delay={40}></Star>
    <Star delay={70}></Star>
    <Star delay={100}></Star>
    <Star delay={130}></Star>
</div>

<style>
    .star-container {
        display: flex;
        gap: .8rem;
    }
</style>
