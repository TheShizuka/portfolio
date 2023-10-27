<script>
    export let setFilter;

    const categories = ['all', 'portrait', 'nature', 'animal', 'japan', 'singapore', 'macro', 'street'];

    let selectedCategory = 'all';
    
    function applyFilter(category) {
        selectedCategory = category;
        setFilter(category);
    }
</script>

<nav class="nav-bar">
    <ul>
        {#each categories as category}
            <li
                class:selected={selectedCategory === category}
                on:click={() => applyFilter(category)}
            >
                {category}
            </li>
        {/each}
    </ul>
</nav>

<style>
    .nav-bar ul {
        list-style-type: none;
        /* Add your CSS for the nav bar */
    }
    li {
        cursor: pointer;
        /* More styling here */
    }
    li:hover {
        /* Hover effect */
    }
    li:selected {
        /* Selected item style */
    }
</style>
