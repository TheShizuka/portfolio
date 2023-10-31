<script>
    export let design = {
        title: "",
        description: "",
        imgSrc: ""
    };
    export let isSelected = false;
    export let selectDesign = () => {};
    export let nextDesign = () => {};
    export let prevDesign = () => {};
</script>

<img src={design.imgSrc} alt={design.title} on:click={selectDesign} />
{#if isSelected}
<div class="overlay">
    <img src={design.imgSrc} alt={design.title} />
    <h2>{design.title}</h2>
    <p>{design.description}</p>
    <button on:click={prevDesign}>&lt;</button>
    <button on:click={nextDesign}>&gt;</button>
    <button on:click={() => isSelected = false}>X</button>
</div>
{/if}
