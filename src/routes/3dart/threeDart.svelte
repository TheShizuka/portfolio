<script>
  import { onMount } from 'svelte';
  let showModal = false;
  let selectedProject = null;

  function openModal(project) {
    selectedProject = project;
    showModal = true;
  }

  function closeModal() {
    showModal = false;
  }
</script>

<style>
.description-container {
  text-align: center;
  padding: 3rem 1rem; /* Adjust padding as needed */
  margin-bottom: 5rem; /* Adds some space between the description and the grid */
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
    gap: 2rem;
    align-items: center;
    padding: 2rem;
    padding-bottom: 9rem;
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
    color: white;
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
.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.8);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000;
}

.modal-content {
  background-color: #ffffff;
  padding: 2rem;
  max-width: 80%;
  max-height: 80%;
  overflow: auto;
}
.page{
  display: flex;
  justify-content: center;
  width: 100%;
  padding-bottom: 3rem;
}
</style>




<div class="description-container">
  <h2>My Photography Journey</h2>
  <p>
Over time, my passion for photography has not only remained a delightful pursuit of curiosity and joy, but has also seen a substantial honing of skills. Each captured moment reflects a blend of enthusiasm and a step forward in my photographic journey. As I reminisce through these frames, the eagerness to further refine my craft only intensifies. I am excited for the continuous journey of discovery and improvement that lies ahead, and I invite you to stroll through my evolving gallery of memories below.</div>

<div class="page">
<div class="project-container">
  <!-- Project 1 -->
  <div class="project project1" on:click={() => openModal('project1')}>
    <img src="../../images/brisee.png" alt="brisée">
    <div class="text">
      <h3>Brisée : An Animated Short</h3>
      <p>During my time as a 3D infographist student, I joined forces with three other classmates to create a short film titled "Brisée". The story unfolds inside a trashcan where our main character, Elisabeth, a discarded porcelain doll, stumbles upon an intriguing new friend among the trash. Learn More...</p>
    </div>
  </div>

  <!-- Project 2 -->
  <div class="project reverse project2" on:click={() => openModal('project2')}>
    <img src="../../images/wagon+ref.png" alt="wagon Image">
    <div class="text">
      <h3>Tokyo Wagon</h3>
      <p>In this project, I took on the challenge of creating a 3D model of a train wagon based on a drawing reference. Learn More...<p>
    </div>
  </div>
</div>

{#if showModal}
  <div class="modal" on:click={closeModal}>
    <div class="modal-content" on:click|stopPropagation>
      <!-- Project 1 Details -->
      {#if selectedProject === 'project1'}
        <h2>Brisée : An Animated Short</h2>
        <p><!-- Full description... --></p>
        <!-- Embed the final short movie and additional videos/gifs -->
        <iframe src="https://your-video-url.com" frameborder="0" allowfullscreen></iframe>
        <!-- ... -->
      {/if}

      <!-- Project 2 Details -->
      {#if selectedProject === 'project2'}
        <h2>Project Title 2</h2>
        <p><!-- Full description... --></p>
        <!-- Embed the final short movie and additional videos/gifs -->
        <iframe src="https://your-video-url.com" frameborder="0" allowfullscreen></iframe>
        <!-- ... -->
      {/if}
    </div>
  </div>
{/if}
</div>
