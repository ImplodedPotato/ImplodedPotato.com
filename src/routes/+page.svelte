<script lang="ts">
    let buttons = [
        {
        h1: "Games.ImplodedPotato.com",
        h2: "A collection of games",
        link: "https://games.implodedpotato.com"
        },
        {
           h1: "Seddit",
           h2: "Satiric Reddit",
           link: "/seddit"
        }
    ]
</script>

<svelte:head>
    <link rel="preload" as="font" href="/FiraCode-Retina.ttf" type="font/ttf" crossorigin="anonymous">
</svelte:head>
<h1>Welcome to ImplodedPotato.com</h1>
<p>Here you will find the 'many' projects of a Potato which has been Imploded</p>

<div class="main-buttons-capsule">
    {#each buttons as button (button.link)}
        <a href="{button.link}">
            <div class="main-buttons">
                <p>{button.h1}</p>
                <p style="margin-top: 10px; margin-bottom: 50px">{button.h2}</p>
            </div>
        </a>
    {/each}
</div>

<a href="https://github.com/ImplodedPotato/implodedpotato.com/">
    <img style="position: fixed; bottom: 8px; right: 8px; scale: 0.6" src="github-mark-white.svg" alt="GitHub">
</a>

<style>
    :global {
        body {
            background-color: #282C34;
            margin: auto;
            padding: 10px;
            font-size: initial;
        }

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

    a {
        color: aquamarine;
        text-decoration: none;
    }

    h1, p, div {
        color: antiquewhite;
        text-align: center;
        font-family: "fira-code",monospace;
    }

    @font-face {
        font-family: 'fira-code';
        font-style: normal;
        font-weight: 200;
        src: url("/FiraCode-Retina.ttf");
    }
</style>