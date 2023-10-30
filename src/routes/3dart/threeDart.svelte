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

.project-container {
    display: flex;
    flex-direction: column;
    gap: 2rem;
  }

  .project {
    display: flex;
    flex-direction: row;
    gap: 1rem;
    align-items: center;
  }

  .project.reverse {
    flex-direction: row-reverse;
  }

  .project img {
    max-width: 300px;
    width: 100%;
  }

  .project .text {
    max-width: 400px;
  }

  @media (max-width: 768px) {
    .project {
      flex-direction: column;
      text-align: center;
    }

    .project.reverse {
      flex-direction: column;
    }
  }
</style>




<div class="description-container">
  <h2>My Photography Journey</h2>
  <p>
Over time, my passion for photography has not only remained a delightful pursuit of curiosity and joy, but has also seen a substantial honing of skills. Each captured moment reflects a blend of enthusiasm and a step forward in my photographic journey. As I reminisce through these frames, the eagerness to further refine my craft only intensifies. I am excited for the continuous journey of discovery and improvement that lies ahead, and I invite you to stroll through my evolving gallery of memories below.</div>


<div class="project-container">
  <!-- Project 1 -->
  <div class="project">
    <img src="/path/to/image1.jpg" alt="Project 1 Image">
    <div class="text">
      <h3>Project Title 1</h3>
      <p>Description of project 1...</p>
    </div>
  </div>

  <!-- Project 2 -->
  <div class="project reverse">
    <img src="/path/to/image2.jpg" alt="Project 2 Image">
    <div class="text">
      <h3>Project Title 2</h3>
      <p>Description of project 2...</p>
    </div>
  </div>
