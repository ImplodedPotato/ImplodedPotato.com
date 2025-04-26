<script lang="ts">
    let buttons = [
        {
            h1: "Games.ImplodedPotato.com",
            h2: "A collection of games",
            link: "https://games.implodedpotato.com",
            hidden: false
        },
        {
            h1: "Seddit",
            h2: "Satiric Reddit",
            link: "/seddit",
            hidden: false
        },
        {
            h1: "Business",
            h2: "Business Site",
            link: "/BUS",
            hidden: false
        },
        {
            h1: "Vid Prod Port",
            h2: "Stupid Prod",
            link: "/vp",
            hidden: true
        }
    ]
</script>

<h1>Welcome to ImplodedPotato.com</h1>
<p>Here you will find the 'many' projects of a Potato which has been Imploded</p>

<div class="main-buttons-capsule">
    {#each buttons as button (button.link)}
        {#if !button.hidden}
            <a href="{button.link}">
                <div class="main-buttons">
                    <p>{button.h1}</p>
                    <p style="margin-top: 10px; margin-bottom: 50px">{button.h2}</p>
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