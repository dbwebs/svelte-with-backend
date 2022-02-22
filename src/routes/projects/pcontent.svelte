<script>
    export let info = {};
    export let nowinfo = [];
    export let prinfo =[];
    export let heroimg = {};
</script>

<div class="container-fluid p-5 text-center bg-primary">
    <h1>{info.titleA}</h1>
    <img class="mw-100" src={heroimg.img} alt={heroimg.alt}>
</div>
<div class="p-3">
    <h2 class="text-light">{info.titleB}</h2>
    <ul>
        {#each nowinfo as i}
            <li class="text-light">{i.content}</li>
        {/each}
    </ul>
    <h2 class="text-light">The Project</h2>
    <p class="text-light">{info.titleBsub}</p>
    <ul>
        {#each prinfo as i}
            <li class="text-light">{i.content}</li>
        {/each}
    </ul>
</div>