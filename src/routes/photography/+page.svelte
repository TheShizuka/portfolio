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
