<script>
    import { onMount } from 'svelte';
    export let photos; // The original photo categories
    export let filter; // Active filter

    // Reactive statement to filter photos based on category
    $: filteredPhotos = filter === 'all' 
        ? photos 
        : photos.filter(photoCategory => photoCategory.category === filter);

    onMount(() => {
        console.log(filteredPhotos); // Log the filtered photos to check if they're correct
    });
</script>

<!-- Now, you will loop over the filteredPhotos, not the original photos -->
{#each filteredPhotos as category}
    <div>
        <h2>{category.category}</h2> <!-- Display the category name -->
        
        <div class="image-grid">
            <!-- Now, loop through each photo in the current category -->
            {#each category.images as photo}
                <div class="image-container">
                    <img src={photo.url} alt={photo.description} style="height: 100%; width: auto;" />
                </div>
            {/each}
        </div>
    </div>
{/each}

<!-- your styles remain unchanged -->
