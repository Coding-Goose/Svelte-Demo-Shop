<script lang="ts">

import {Link, link} from "svelte-navigator";
import {warenkorb} from "../stores";

let anzahl = 0;
warenkorb.subscribe((arr: []) => anzahl = arr.length);
</script>

<header>
    <h1>
        Shopping Goose
    </h1>
    <div class="links">
        <a href="/" use:link>Home</a>
        <a href="product" use:link>Produkte</a>
        <a href="">Impressum</a>
        <div class="warenkorb">
            <div class="warenkorb-image">
                <div class="warenkorb-count">
                    {anzahl}
                </div>
            </div>
        </div>
    </div>
</header>

<style>
    h1 {
        font-weight: bold;
        margin: 0;
    }
    header {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    a {
        color: whitesmoke;
        font-size: 1.4rem;
    }


    .warenkorb {
        background-color: whitesmoke;
        width: 3rem;
        height: 3rem;
        border-radius: 50%;
        display: flex;
        justify-content: center;
        align-items: center;
        position: relative;
    }

    .warenkorb-image {
        background-image: url("../assets/warenkorb.png");
        background-size: contain;
        width: 1.8rem;
        height: 1.8rem;
    }

    .links {
        display: flex;
        gap: .5rem;
        align-items: center;
    }

    .warenkorb-count {
        background: #E8C8D3;
        border-radius: 50%;
        height: 1.5rem;
        width: 1.5rem;
        display: flex;
        justify-content: center;
        align-items: center;
        position: absolute;
        bottom: -.3rem;
        right: -.3rem;
    }
</style>
