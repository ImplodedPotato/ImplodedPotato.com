<script>
    let { children } = $props();
</script>

<a id="back" href="/../">Back to ImplodedPotato.com</a>

<style>
    #back {
        position: fixed;
        left: 3vw;
        bottom: 2vw;
        transition: all 125ms ease-out;
        z-index: 1;
    }
</style>

{@render children()}