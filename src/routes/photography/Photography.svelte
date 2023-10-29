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
    position: relative;
    overflow: hidden;
    background-color: #f0f0f0;
    cursor: pointer;
  }
  .grid-item img {
    display: block;
    max-width: 100%;
    border: 0;
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
      <img data-src="../../images/all/{image}.png" class="lazy" alt="Image {image}">
    </div>
  {/each}
</div>

{#if selectedImage}
  <div class="lightbox" on:click={closeLightbox}>
    <button class="close-button">X</button>
    <img src="../../images/all/{selectedImage}.png" alt="Image {selectedImage}">
  </div>
{/if}
