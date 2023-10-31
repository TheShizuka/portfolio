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

{#each designs as design, index}
<DesignItem 
    design={design} 
    isSelected={selectedIndex === index}
    selectDesign={() => selectDesign(index)}
    nextDesign={nextDesign}
    prevDesign={prevDesign}
/>
{/each}
