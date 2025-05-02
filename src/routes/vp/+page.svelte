<script lang="ts">
    import sections from "$lib/data/vp-sections.json"
</script>


<div style="padding-bottom: 5vh" id="title">
    <img style="margin-left: auto; padding-right: 10vh;"
         src="https://placehold.co/200x200" alt="jm"/>
    <h1 style="margin-right: auto; padding-top: 25px">James Miller</h1>
</div>

{#each sections as sect (sect.id)}
    <div id="{sect.id}">
        <h2>{sect.name}</h2>
        <div class="content-container">
            {#each sect.content as content (content.name)}
                <div class="inner-content-container">
                    <img src="{content.pic}" alt="{content.name}">
                    <p>{content.name}</p>
                    {#if content.explanation !== null}
                        <p>{content.explanation}</p>
                    {/if}
                </div>
            {/each}
        </div>
    </div>
{/each}

<div id="inspirational-individual">
    <h2>Inspirational Individual</h2>
</div>

<div id="inspirational-quote">
    <h2>Inspirational Quote</h2>
</div>

<style>
    #title {
        display: flex;
        /*align-items: center;*/
        padding-top: 50px;
    }

    #about-me,
    #dream-colleges,
    #career-interests,
    #inspirational-individual,
    #inspirational-quote {
        padding-bottom: 10vh;
    }

    .content-container {
        display: flex;
        max-width: max-content;
        margin: auto;
    }

    .inner-content-container {
        background: #142f2a;
        margin: 0 10px 0 10px;
        clip-path: rect(0px auto auto 0px round 5%);
        transition: all 125ms;
    }

    .inner-content-container:hover {
        background: #275E52;
    }
</style>

