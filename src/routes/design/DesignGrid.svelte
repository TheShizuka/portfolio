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
</script>

<div class="design-grid">
    {#each designs as design, index}
        <DesignItem 
            design={design} 
            isSelected={selectedIndex === index}
            selectDesign={() => selectDesign(index)}
            nextDesign={nextDesign}
            prevDesign={prevDesign}
        />
    {/each}
</div>

<style>
    .design-grid {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
        gap: 2rem;
        padding: 2rem;
        justify-content: center;
    }

    @media screen and (max-width: 600px) {
        .design-grid {
            grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
        }
    }
</style>
