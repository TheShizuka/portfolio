<script>
  import { onMount } from 'svelte';
  import LazyLoad from "vanilla-lazyload";

  let images = Array.from({ length: 95 }, (_, i) => i + 1);
  let selectedImage = null;

  onMount(() => {
    const lazyLoadInstance = new LazyLoad();
  });

  function openLightbox(image) {
    selectedImage = image;
  }

  function closeLightbox() {
    selectedImage = null;
  }
</script>

<style>
  .grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 16px;
    place-items: start;
  }
  .grid-item {
    width: 100%;
    padding-top: 100%; /* 1:1 Aspect Ratio */
    position: relative;
    cursor: pointer;
    background-color: #f0f0f0;
    overflow: hidden; /* Hide anything outside the box */
}

.grid-item .image-container {
    position: absolute;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    display: flex;
    justify-content: center;
    align-items: center;
}

.grid-item img {
    object-fit: cover;
    width: 100%;
    height: 100%;
    transition: transform 0.3s;
}

.grid-item:hover img {
    transform: scale(1.1);
}

  .lightbox {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.8);
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 1000;
  }
  .lightbox img {
    max-width: 90%;
    max-height: 90%;
    border: 0;
  }
  .close-button {
    position: absolute;
    top: 20px;
    right: 20px;
    background-color: #ffffff;
    border: none;
    font-size: 24px;
    cursor: pointer;
  }
</style>

<div class="grid">
  {#each images as image (image)}
    <div class="grid-item" on:click={() => openLightbox(image)}>
      <div class="image-container">
        <img data-src="../../images/all/{image}.webp" class="lazy" alt="Image {image}">
      </div>
    </div>
  {/each}
</div>

{#if selectedImage}
  <div class="lightbox" on:click={closeLightbox}>
    <button class="close-button">X</button>
    <img src="../../images/all/{selectedImage}.webp" alt="Image {selectedImage}">
  </div>
{/if}

