<script>
    export let photos;
    export let filter;
    import photos from './images/photos.json';

    $: filteredPhotos = filter === 'all' ? photos : photos.filter(photo => photo.category === filter);
    console.log(portrait1.photo.url)
</script>

<!-- Loop through each category of photos -->
{#each photos as category}
    <div>
        <h2>{category.category}</h2> <!-- Display the category name -->
        
        <div class="image-grid">
            <!-- Now, loop through each photo in the current category -->
            {#each category.images as photo}
                <div class="image-container">
                    <!-- Now we're accessing the URL correctly through the nested structure -->
                    <img src={photo.url} alt={photo.description} style="height: 100%; width: auto;" />
                </div>
            {/each}
        </div>
    </div>
{/each}


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
