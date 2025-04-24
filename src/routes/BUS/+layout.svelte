<script>
    let { children } = $props();

    // console.log(window.matchMedia("(max-width: 600px)"));
</script>

<svelte:head>
    <link rel="preload" as="font" href="/FiraCode-Retina.ttf" type="font/ttf" crossorigin="anonymous">
    <link rel="stylesheet" href="/shared.css">
</svelte:head>

<div id="nav_bar">
    <a href="/BUS">
        <div style="display: flex; align-items: center; float: right">
            <img id="logo"  src="/Company Logo In White.png" alt="Logo">
            <h2>Business</h2>
        </div>
    </a>


    <nav style="margin-left: auto; float: left;">
        <a class="nav_button" href="/BUS/Products">Products</a>
        <a class="nav_button" style="padding-right: 5px" href="/BUS/Mission-Statement">Mission Statement</a>
    </nav>
</div>

<!--<div style="position: fixed; width: 200px; height: 200px; margin-left: calc(50% - 100px); background-color: rgba(0, 0, 0, .5); filter: blur(1rem)"></div>-->

<div style="margin-top: calc(8vh + 20px)"></div>

<style>
    /*
    Animations inspired by:
    https://prismic.io/blog/css-hover-effects
     */
    :global {
        body::before {
            position: fixed;
            content: '';
            width: calc(100% + 10px);
            height: calc(8vh + 20px + 10px + 5px);
            /* height of nav + little extra + translate offest + little extra */
            backdrop-filter: blur(15px);
            filter: blur(5px);
            transform: translate(-20px, -20px);
            box-sizing: border-box;
        }
    }
    .nav_button {
        margin-left: 10px;
        margin-right: 10px;
        transition: all 125ms ease-out;
        position: relative;
        display: inline-block;
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


    #nav_bar {
        position: fixed;
        display: flex;
        align-items: center;
        background-color: #161A20;
        border-radius: 10px;
        width: calc(100% - 40px);
        height: 7vh;
        margin: 10px;
        box-shadow: 0px 0px 10px 5px #142F2A,
                    0px 0px 50px 10px rgba(0, 0, 0, 0.5);
        transition: all 125ms ease-in;
        backdrop-filter: blur(100vh);
    }

    #nav_bar:hover {
        box-shadow: 0px 0px 10px 5px #19483F;
    }

    #logo {
        width: 50px;
        height: 50px;
        transition: transform 250ms ease-in-out;
    }

    #logo:hover {
        transform: rotate(180deg);
    }

</style>

{@render children()}