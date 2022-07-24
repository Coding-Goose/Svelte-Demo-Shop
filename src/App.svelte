<script lang="ts">
    import {Route, Router} from "svelte-navigator";
    import ProductCard from "./components/ProductCard.svelte";
    import Header from "./components/Header.svelte";
    import Home from "./components/Home.svelte";
</script>

<Router>
    <main>
        <Header/>
        <Route path="/">
            <Home/>
        </Route>
        <Route path="product">
            <ProductCard/>
        </Route>
    </main>
</Router>

<style>
    main {
        max-width: 50rem;
        margin: auto;
    }
</style>
