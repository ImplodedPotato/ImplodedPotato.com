<h2>Products</h2>

<script lang="ts">
    let products = [
        {
            name: "product",
            image: "https://placehold.co/1024x1024",

        },
        {
            name: "product 2",
            image: "https://placehold.co/1024x1024",

        },
        {
            name: "product 3",
            image: "https://placehold.co/1024x1024",

        },
        {
            name: "product 4",
            image: "https://placehold.co/1024x1024",

        },
        {
            name: "product 5",
            image: "https://placehold.co/1024x1024",

        },
        {
            name: "product 6",
            image: "https://placehold.co/1024x1024",

        },
    ]
</script>

<div id="products_container">
    {#each products as prod (prod.name)}
        <div class="prod_container">
            <img class="prod_pict" src={prod.image} alt="{prod.name}">
<!--            <div class="prod_pict"></div>-->

            <p class="prod_txt">{prod.name}</p>
            <p class="prod_txt">{prod.name}</p>
        </div>
    {/each}
</div>

<style>
    #products_container {
        display: grid;
        grid-template-columns: repeat(2, max-content);
        margin: auto;
        max-width: max-content;
    }
    .prod_container {
        margin: 20px;
        width: 192px;
        /*background: #3D3F4E;*/
    }

    .prod_pict {
        width: 192px;
        margin-bottom: 20px;
        /*clip-path: path("M100,200c43.8,0,68.2,0,84.1-15.9C200,168.2,200,143.8,200,100s0-68.2-15.9-84.1C168.2,0,143.8,0,100,0S31.8,0,15.9,15.9C0,31.8,0,56.2,0,100s0,68.2,15.9,84.1C31.8,200,56.2,200,100,200z");*/
        clip-path: rect(0px auto auto 0px round 20%);
        offset-position: left 64px top 64px;
    }

    .prod_txt {
        margin: auto
    }
</style>