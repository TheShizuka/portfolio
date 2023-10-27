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
