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
.close-button {
    position: absolute;
    top: 1rem;
    right: 1rem;
    color: white;
    border: none;
    font-size: 1.5rem;
    line-height: 1;
    cursor: pointer;
  }
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
    flex-direction: column;
    gap: 2rem;
    align-items: center;
    padding: 2rem;
    padding-bottom: 9rem;
    transition: transform 0.3s ease-in-out; /* Add transition effect */
    cursor: pointer; /* Change cursor to indicate clickability */
  }
.project:hover {
        transform: scale(1.10); /* Scale up the div slightly when hovered over */
    }

  .project.reverse {
    flex-direction: row-reverse;
  }

  .project img {
    max-width: 1000px;
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
.wagon{
      display: flex;
    justify-content: center;
    align-content: center;
    flex-direction: row;
    flex-wrap: wrap;
    gap: 1rem;
  
}
.wagon-img {
  display: flex;
    justify-content: center;
    align-content: center;
    flex-direction: column;
    flex-wrap: wrap;
    text-align: center;
    font-size: 1.2rem;
    flex: 1;
}
.wagon-img img{
  max-width: 500px;
  width: 100%;
}
.wagon-img h4{
  color: white;
}
.titre-desc{
  text-align: center;
  color: white;
}
.video-container {
        position: relative;
        width: 100%;
        padding-bottom: 56.25%; /* 16:9 Aspect Ratio */
        height: 0;
    }

    .video-container video {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
    }

    @media (max-width: 768px) {
        .video-container {
            padding-bottom: 75%; /* Adjust aspect ratio for smaller screens if necessary */
        }
    }
</style>




<div class="description-container">
  <h2>My 3D Artistry Adventure</h2>
  <p>Embarking on my journey through the Infographie 3D Bachelor program at Institut Artline, I delved into various 3D specialties using industry-standard software. My hard surface modeling and rendering skills were honed in Autodesk Maya with Arnold Render, while Cinema 4D paired with Octane Render elevated my visualization projects. Unreal Engine broadened my horizon in real-time rendering, whereas Substance Painter and Designer became my go-to for texturing and material creation. Nuke the Foundry enhanced my compositing prowess, and ZBrush was instrumental in my sculpting projects. Each software added a unique flavor to my projects, fueling my passion for digital artistry and preparing me for a continuous journey of learning and improvement in this captivating field.</p>
</div>
<div class="page">
<div class="project-container">
  <!-- Project 1 -->
  <div class="project project1" on:click={() => openModal('project1')}>
    <img src="../../images/bugdays.png" alt="bugdays">
    <div class="text">
      <h3>Website Design - BUG Days</h3>
        <p>This website design was a project made for my University, they organised a video games tournment hosting League of Legends and Rocket League and this one my design proposition</p>
    </div>
  </div>
</div>


{#if showModal}
  <div class="modal" on:click={closeModal}>
    <div class="modal-content" style="background-image: url('../../images/background.png'); background-repeat: repeat;" on:click|stopPropagation>
    <button class="close-button" style="background-image: url('../../images/background.png'); background-repeat: repeat;" on:click={closeModal}>&times;</button>
      <!-- Project 1 Details -->
      {#if selectedProject === 'project1'}
      <div class="titre-desc">
          <img src="../../images/website.png" alt="website">
          </div>
        <!-- ... -->
      {/if}


    </div>
  </div>
{/if}
</div>
