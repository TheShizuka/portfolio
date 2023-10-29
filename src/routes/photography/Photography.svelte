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

  function nextImage() {
    let index = images.indexOf(selectedImage);
    if (index < images.length - 1) {
      selectedImage = images[index + 1];
    }
  }

  function prevImage() {
    let index = images.indexOf(selectedImage);
    if (index > 0) {
      selectedImage = images[index - 1];
    }
  }
</script>


<style>
  .grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 16px;
    place-items: start;
    max-width: 1000px;
    margin-top: 3rem;
    margin-bottom: 3rem;
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
.nav-button {
  position: absolute;
  top: 50%;
  background-color: #ffffff;
  border: none;
  padding: 10px;
  cursor: pointer;
  transform: translateY(-50%);
}

.nav-button.left {
  left: 20px;
}

.nav-button.right {
  right: 20px;
}
</style>

<div class="grid">
  {#each images as image (image)}
    <div class="grid-item" on:click={() => openLightbox(image)}>
      <div class="image-container">
        <img data-src="../../images/all200/{image}.webp" class="lazy" alt="Image {image}">
      </div>
    </div>
  {/each}
</div>

{#if selectedImage}
  <div class="lightbox" on:click={closeLightbox}>
    <button class="close-button">X</button>
    <button class="nav-button left" on:click|stopPropagation={prevImage}>&lt;</button>
    <button class="nav-button right" on:click|stopPropagation={nextImage}>&gt;</button>
    <img src="../../images/all/{selectedImage}.webp" alt="Image {selectedImage}">
  </div>
{/if}


