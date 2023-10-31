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


<style>
img {
    width: 100%;
    cursor: pointer;
}

.overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    background: rgba(0, 0, 0, 0.9);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

.overlay img {
    max-width: 70%;
    max-height: 70%;
    margin-bottom: 1rem;
}

.overlay h2, .overlay p {
    color: white;
    text-align: center;
    margin: 0.5rem;
}

</style>



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
