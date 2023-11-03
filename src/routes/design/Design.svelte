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
@media (max-width: 768px) {
  .description-container h2 {
    font-size: 1.2rem; /* Adjust font size as needed */
  }

  .description-container p {
    font-size: 0.7rem; /* Adjust font size as needed */
  }
}
  .logos-container{
    width: 100%;
    justify-content: center;
    display: inline-grid;
    text-align: center;
  }
.logos-container p{
  color: white;
  max-width: 1000px;
}
.logos-container h3{
  color: white;
}
</style>




<div class="description-container">
  <h2>My Design Odyssey</h2>
  <p>
As I embarked on my journey into the world of design, I quickly realized its complexities and the nuances that make a design stand out. While I consider myself to be at the early stages of this adventure, each logo or design piece I've created reflects my earnest efforts to learn and grow. These projects, primarily exercises and practice runs, represent my initial steps into this vast field. I'm eager to continue honing my skills, learning from every project, and gradually building my design repertoire. Here's a glimpse of my starting ventures in design.</p></div>


<script>
    import DesignGrid from './DesignGrid.svelte';
    import Website from './webSite.svelte';

    let designs = [
        {title: "", description: "", imgSrc: "../../images/logos/5.png"},
        {title: "", description: "", imgSrc: "../../images/logos/4.png"},
        {title: "", description: "", imgSrc: "../../images/logos/2.png"},
        {title: "", description: "", imgSrc: "../../images/logos/6.png"},
        {title: "", description: "", imgSrc: "../../images/logos/7.png"},
        {title: "", description: "", imgSrc: "../../images/logos/8.png"},
        {title: "", description: "", imgSrc: "../../images/logos/9.png"},
        {title: "", description: "", imgSrc: "../../images/logos/10.png"},
        {title: "", description: "", imgSrc: "../../images/logos/1.png"},
        {title: "", description: "", imgSrc: "../../images/logos/3.png"},
        // ... other designs
    ];
</script>
<div class="logos-container">
<h3>Logos</h3>
<p>These logos were created as part of a training exercise to master Adobe Illustrator and Photoshop. Through this process, I have acquired foundational skills and an understanding of the principles necessary for crafting vector designs.</p>
<DesignGrid designs={designs} />
</div>
<Website />
