<script lang="ts">
    import buttons from "$lib/data/home-buttons.json"
</script>

<h1>Welcome to ImplodedPotato.com</h1>
<p>Here you will find the 'many' projects of a Potato which has been Imploded</p>

<div class="main-buttons-capsule">
    {#each buttons as button (button.link)}
        {#if !button.hidden}
            <a href="{button.link}">
                <div class="main-buttons">
                    <p>{button.h1}</p>
                    <p style="margin-bottom: 50px; line-height: 1.5">{button.h2}</p>
                </div>
            </a>
        {/if}
    {/each}
</div>


<style>
    :global {
        @media screen and (max-width: 400px) {
            body {
                font-size: small;
            }
        }
    }

    .main-buttons-capsule {
        padding-top: 5vh;
        display: grid;
        grid-template-columns: repeat(auto-fill, min-content);
        gap: 10px;
        margin: auto;
        max-width: max-content;
    }

    @media screen and (min-width: 600px) {
        .main-buttons-capsule {
            grid-template-columns: repeat(2, min-content);
        }
    }

    @media screen and (min-width: 900px) {
        .main-buttons-capsule {
            grid-template-columns: repeat(3, min-content);
        }
    }

    .main-buttons {
        background-color: #49485e;
        padding: 5px;
        border-radius: 10px;
        display: block;
        width: 250px;
        height: 250px;
        font-size: medium;
        align-content: center;
    }

    .main-buttons:hover {
        background-color: #54617e;
    }


</style>