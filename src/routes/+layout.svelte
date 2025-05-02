<script>
    let { children } = $props();
</script>

<svelte:head>
    <link rel="preload" as="font" href="/FiraCode-Retina.ttf" type="font/ttf" crossorigin="anonymous">
    <link rel="stylesheet" href="/shared.css">
</svelte:head>

<a href="https://github.com/ImplodedPotato/implodedpotato.com/">
    <img id="git-hub" src="/github-mark-white.svg" alt="GitHub">
</a>

{@render children()}

<style>
    #git-hub {
        position: fixed;
        bottom: 8px;
        right: 8px;
        scale: 0.6;
        z-index: 1;
    }
</style>