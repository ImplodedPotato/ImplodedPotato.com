<h2>Products</h2>

<script lang="ts">
    let products = [
        {
            name: "string",
            image: "https://placehold.co/1024x1024",

        },
        {
            name: "string2",
            image: "https://placehold.co/1024x1024",

        },
        {
            name: "string3",
            image: "https://placehold.co/1024x1024",

        },
    ]
</script>

<div id="products_container">
    {#each products as prod (prod.name)}
        <div class="prod_container">
            <img style="height: 128px" class="prod_pict" src={prod.image} alt="{prod.name}">
<!--            <div class="prod_pict"></div>-->

            <p style="grid-column: 2 / 3; grid-row: 1 / 2; background: #6495ed; height: min-content">{prod.name}</p>
            <p style="grid-column: 2 / 3; grid-row: 2 / 4; background: #6495ed; height: min-content">{prod.name}</p>
        </div>
    {/each}
</div>

<style>
    #products_container {

    }

    .prod_container {
        display: grid;
        grid-template-columns: auto max-content;
        grid-template-rows: auto max-content;
        grid-column-gap: 10px;
        padding: 20px;
    }

    .prod_pict {
        grid-column: 1 / 2;
        grid-row: 1 / 3;
        background: #6495ed;
    }
</style>