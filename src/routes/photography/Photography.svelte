<script>
  import { onMount } from 'svelte';
  import LazyLoad from "vanilla-lazyload";

  let images = Array.from({ length: 72 }, (_, i) => i + 1);
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
.description-container {
  text-align: center;
  padding: 3rem 1rem; /* Adjust padding as needed */
  margin-bottom: 2rem; /* Adds some space between the description and the grid */
}

.description-container h2 {
  font-size: 1.8rem; /* Adjust font size as needed */
  margin-bottom: 1rem; /* Adds some space between the title and the description */
  color: #ffffff;
}

.description-container p {
  max-width: 800px;
  margin: 0 auto; /* Centers the paragraph if it's narrower than its container */
  font-size: 1rem; /* Adjust font size as needed */
  color: #ffffff;
}
  .grid-container {
    display: flex;
    justify-content: center;
    width: 100%;
    padding-bottom: 3rem; /* or adjust the padding to your liking */
  }
  .grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 16px;
    place-items: start;
    max-width: 1000px;
    width: 100%; /* ensures the grid grows to fill its container */
    /* ...rest of your grid styles... */
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
@media (max-width: 768px) {
  .grid{
    grid-template-columns: repeat(auto-fill,minmax(120px,1fr));
  }
  .description-container h2 {
    font-size: 1.2rem; /* Adjust font size as needed */
  }

  .description-container p {
    font-size: 0.7rem; /* Adjust font size as needed */
  }
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
    color: #ffffff;
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
  color: #ffffff;
}

.nav-button.right {
  right: 20px;
  color: #ffffff;
}
</style>
<div class="description-container">
  <h2>My Photography Journey</h2>
  <p>Over time, my passion for photography has evolved into a delightful pursuit that continuously fuels my curiosity and joy. This journey has significantly been shaped by my travels, with numerous visits to the historic and serene Kyoto, and the modern vibrance of Singapore. The tranquil temples, Zen gardens, and seasonal beauty of Kyoto, juxtaposed with Singapore's urban tapestry, have been the main stages for most of my photographs. Each image not only embodies a fusion of enthusiasm and a leap in my photographic expertise but also conveys the unique tranquility and rhythm of these locations. Reflecting on these frames only magnifies my desire to further polish my artistry. I am eager for the endless path of exploration and enhancement that awaits, and I cordially invite you to peruse my gallery of memories, each a chapter of my evolving narrative.</p>
</div>
<div class="grid-container">
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
    <button style="background-image: url('../../images/background.png'); background-repeat: repeat;" class="close-button">X</button>
    <button style="background-image: url('../../images/background.png'); background-repeat: repeat;" class="nav-button left" on:click|stopPropagation={prevImage}>&lt;</button>
    <button style="background-image: url('../../images/background.png'); background-repeat: repeat;" class="nav-button right" on:click|stopPropagation={nextImage}>&gt;</button>
    <img src="../../images/all/{selectedImage}.webp" alt="Image {selectedImage}">
  </div>
{/if}
</div>

