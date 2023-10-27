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
<style>
/* Base styles */
body {
  font-family: 'Arial', sans-serif;
  margin: 0;
  padding: 0;
  background-color: #f4f4f4;
}

/* Styles for the banner */
.banner {
  background-color: #333;
  color: #fff;
  padding: 1rem;
  text-align: center;
}

/* Navigation bar styles */
.nav-bar {
  background: #ffffff;
  box-shadow: 0px 3px 6px 0px rgba(0, 0, 0, 0.1);
}

.nav-bar ul {
  padding: 0;
  margin: 0;
  list-style: none;
  display: flex;
  justify-content: space-around;
  align-items: center;
}

.nav-bar li {
  cursor: pointer;
  padding: 1rem;
  transition: all 0.3s ease-in-out;
}

.nav-bar li:hover {
  transform: scale(1.1);
}

.nav-bar li:selected {
  text-decoration: underline;
  font-weight: bold;
}

/* Image grid styles */
.image-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); /* This creates a responsive number of columns */
  gap: 15px; /* Adjust gap size as needed */
  padding: 20px;
}

.image-container {
  position: relative; /* Might be used for overlay effects or image captions */
  width: 100%;
  overflow: hidden; /* Clip the images (useful when they have different sizes) */
}

.image-container img {
  width: 100%; /* Make sure images cover their container */
  height: 100%;
  object-fit: cover; /* This will handle image ratios */
  transition: transform 0.3s ease-in-out; /* Optional: for hover effects */
}

.image-container img:hover {
  transform: scale(1.05); /* Optional: zoom effect on hover */
}

/* Responsiveness for smaller screens */
@media (max-width: 768px) {
  .nav-bar ul {
    flex-direction: column;
  }

  .nav-bar li {
    padding: 0.5rem;
  }

  /* Additional adjustments for the image grid or other components as needed */
}

</style>
