<script>
    import DesignItem from './DesignItem.svelte';

    export let designs = [];

    let selectedIndex = -1;

    const selectDesign = (index) => {
        selectedIndex = index;
    };

    const nextDesign = () => {
        if (selectedIndex < designs.length - 1) {
            selectedIndex++;
        }
    };

    const prevDesign = () => {
        if (selectedIndex > 0) {
            selectedIndex--;
        }
    };
const deselectDesign = () => {
        selectedIndex = -1;
    };
</script>

<div class="design-grid">
    {#each designs as design, index}
        <DesignItem 
            design={design} 
            isSelected={selectedIndex === index}
            selectDesign={() => selectDesign(index)}
            nextDesign={nextDesign}
            prevDesign={prevDesign}
            deselectDesign={deselectDesign}
        />
    {/each}
</div>

<style>
    .design-grid {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(250px, 1fr)); /* Modified value */
        gap: 2rem;
        padding: 2rem;
        justify-content: center;
        box-sizing: border-box; /* To ensure padding doesn't affect width */
    }

    @media screen and (max-width: 776px) {
        .design-grid {
            grid-template-columns: repeat(auto-fill, minmax(120px, 1fr)); /* Slightly reduced */
        }
    }
</style>

