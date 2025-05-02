<script lang="ts">
    let { children } = $props();

    import { fade, scale } from "svelte/transition";

    let width = $state(0);

    let isHamDown = $state(false);

    let navButtons = [
        {
            title: "Products",
            url: "/BUS/Products"
        },
        {
            title: "Mission Statement",
            url: "/BUS/Mission-Statement"
        }
    ]
</script>

<svelte:window bind:innerWidth={width}/>


<div id="nav_bar_blur"></div>

<div id="nav_bar">
    <a href="/BUS">
        <div style="display: flex; align-items: center; float: right">
            <img id="logo"  src="/Company Logo In White.png" alt="Logo">
            <h2>Business</h2>
        </div>
    </a>

    {#if width > 550 || width === 0}
        <nav style="margin-left: auto; float: left;">
            {#each navButtons as butt (butt.url)}
                {#if navButtons[navButtons.length - 1] === butt}
                    <a class="nav_button" style="padding-right: 5px" href={butt.url}>{butt.title}</a>
                {:else}
                    <a class="nav_button" href={butt.url}>{butt.title}</a>
                {/if}
            {/each}
        </nav>
    {:else}
        {#if !isHamDown}
            <button in:scale out:scale class="ham-container"
                    style="margin-left: auto" type="button" onclick={() => isHamDown = !isHamDown} >
                <img id="ham" src="/ham.svg" alt="ham"/>
            </button>
        {:else}
            <button in:scale out:scale class="ham-container"
                    style="margin-left: auto" type="button" onclick={() => isHamDown = !isHamDown} >
                <img id="ham" style="width: 35px; padding-right: 15px;" src="/hamDown.svg" alt="ham"/>
            </button>
            <div in:fade={{ duration: 175 }} out:fade={{ duration: 175 }} id="nav_ham_container">
                {#each navButtons as butt (butt.url)}
                    <a class="nav_button" href={butt.url} onclick={() => isHamDown = false}>{butt.title}</a>
                {/each}
            </div>
        {/if}
    {/if}
</div>

<div style="margin-top: calc(8vh + 20px)"></div>

<a id="back" href="/../">Back to ImplodedPotato.com</a>

<style>
    /*
    Animations inspired by:
    https://prismic.io/blog/css-hover-effects
     */
    .nav_button {
        margin-left: 10px;
        margin-right: 10px;
        transition: all 125ms ease-out;
        position: relative;
        display: inline-block;
        color: aquamarine;
    }

    .nav_button:hover {
        color: cornflowerblue;
    }

    .nav_button::after {
        content: '';
        position: absolute;
        width: 100%;
        height: 2px;
        background: cornflowerblue;
        bottom: -5px;
        left: 0;
        transform: scaleX(0);
        transform-origin: center;
        transition: transform 200ms ease-out;
    }


    .nav_button:hover::after {
        transform: scaleX(0.9);
    }

    .ham-container {
        position: absolute;
        right: 0;
    }

    #ham {
        margin-right: 10px;
        transition: all 125ms ease-out;
        position: relative;
        display: inline-block;
        color: aquamarine;
        margin-left: auto;
        padding-right: 10px;
        width: 50px;
    }

    #ham:hover {
        color: cornflowerblue;
    }

    #nav_ham_container {
        display: flex;
        position: absolute;
        right: 0;
        top:  calc(8vh + 20px);
        flex-direction: column;
        gap: 20px;
        font-size: large;
        align-items: end;
        padding: 15px;
        background-color: #161A1F;
        box-shadow: 0px 0px 10px 5px #19483F;
        border-radius: 10px;
    }

    #nav_bar {
        position: fixed;
        display: flex;
        align-items: center;
        background-color: #161A20;
        border-radius: 10px;
        width: calc(100% - 40px);
        height: calc(5vh + 20px);
        margin: 10px;
        box-shadow: 0px 0px 10px 5px #142F2A,
                    0px 0px 50px 10px rgba(0, 0, 0, 0.5);
        transition: all 125ms ease-in;
    }

    #nav_bar:hover {
        box-shadow: 0px 0px 10px 5px #19483F;
    }

    #nav_bar_blur {
        position: fixed;
        content: '';
        width: calc(100% + 10px);
        height: calc(8vh + 20px + 10px + 10px);
        /* height of nav + match nav + translate offest + little extra */
        backdrop-filter: blur(15px);
        filter: blur(6px);
        transform: translate(-20px, -20px);
        box-sizing: border-box;
    }

    #logo {
        width: 50px;
        height: 50px;
        transition: transform 250ms ease-in-out;
    }

    #logo:hover {
        transform: rotate(180deg);
    }

    #back {
        position: fixed;
        left: 3vw;
        bottom: 2vw;
        transition: all 125ms ease-out;
        z-index: 1;
    }

</style>

{@render children()}