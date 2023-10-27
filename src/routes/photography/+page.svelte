<script>
    import { onMount } from 'svelte';
    import NavBar from './NavBar.svelte';  // assuming you have a NavBar component
    import ImageGrid from './ImageGrid.svelte';  // we will create this component

    let photos = [];
    let filter = 'all';
    
    // This should be your actual API call or local data fetch
    onMount(async () => {
        photos = await fetch('path-to-your-photos-api-or-json').then(res => res.json());
    });

    function setFilter(category) {
        filter = category;
    }
</script>

<!-- Here's your banner -->
<div class="banner">
    <!-- Banner content here -->
</div>

<NavBar {setFilter} />

<ImageGrid {photos} {filter} />
<script>
    export let setFilter;

    const categories = ['all', 'portrait', 'landscape', 'animal', 'japan', 'singapore'];

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
<script>
    export let photos;
    export let filter;

    $: filteredPhotos = filter === 'all' ? photos : photos.filter(photo => photo.category === filter);
</script>

<div class="image-grid">
    {#each filteredPhotos as photo}
        <div class="image-container">
            <img src={photo.url} alt={photo.description} style="height: 100%; width: auto;" />
            <!-- assuming your photo object has a url and description field -->
        </div>
    {/each}
</div>

<style>
    .image-grid {
        display: flex;
        flex-wrap: wrap;
        /* Add your grid CSS here */
    }
    .image-container {
        /* Style your image containers */
    }
    /* Add responsiveness using media queries */
</style>

