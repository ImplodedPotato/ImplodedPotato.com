<script lang="ts">
    import sections from "$lib/data/vp-sections.json"
</script>


<div style="padding-bottom: 5vh" id="title">
    <img style="margin-left: auto; padding-right: 10vh;"
         src="https://placehold.co/200x200" alt="jm"/>
    <div style="margin-right: auto">
        <h1 style="margin-right: auto; padding-top: 25px">James Miller</h1>
        <h3 style="max-width: 250px">Student at Cheyenne High School</h3>
    </div>
</div>

{#each sections as sect (sect.id)}
    <div id="{sect.id}">
        <h2>{sect.name}</h2>
        <div class="content-container">
            {#each sect.content as content (content.name)}
                <div class="inner-content-container">
                    {#if content.vid != null}
                        <video controls width="300px">
                            <source src="{content.vid}"/>
                        </video>
                    {:else}
                        <img src="{content.pic}">
                    {/if}
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
<!--    <p>Steve Jobs</p>-->
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
        max-width: 300px;
    }

    .inner-content-container:hover {
        background: #275E52;
    }
</style>

