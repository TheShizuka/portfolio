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
</style>




<div class="description-container">
  <h2>My 3D Artistry Adventure</h2>
  <p>Embarking on a journey through the Infographie 3D Bachelor program at Institut Artline was like stepping into a new realm of creativity. From hard surface modeling to animation and compositing, I dabbled in various 3D specialities before finding my footing. Each project, whether big or small, has been a blend of challenges and discoveries, continually fueling my passion and honing my skills in this digital art domain. With a handful of projects under my belt, each one has been a stepping stone, and I look forward to the continuous learning and improvement that lies ahead in this visually captivating field.<p>
</div>
<div class="page">
<div class="project-container">
  <!-- Project 1 -->
  <div class="project project1" on:click={() => openModal('project1')}>
    <img src="../../images/brisee.png" alt="brisée">
    <div class="text">
      <h3>Brisée : An Animated Short</h3>
      <p>During my time as a 3D infographist student, I joined forces with three other classmates to create a short film titled "Brisée". The story unfolds inside a trashcan where our main character, Elisabeth, a discarded porcelain doll, stumbles upon an intriguing new friend among the trash. <b>Learn More...</b></p>
    </div>
  </div>

  <!-- Project 2 -->
  <div class="project reverse project2" on:click={() => openModal('project2')}>
    <img src="../../images/wagon+ref.png" alt="wagon">
    <div class="text">
      <h3>Tokyo Wagon</h3>
      <p>In this project, I took on the challenge of creating a 3D model of a train wagon based on a drawing reference. <b>Learn More...</b><p>
    </div>
  </div>


<!-- Project 3 -->
  <div class="project project3" on:click={() => openModal('project3')}>
    <img src="../../images/inari.png" alt="inari">
    <div class="text">
      <h3>Fushimi Inari Taisha shrine - Unreal Engine</h3>
      <p>Inspired by the peaceful nights at the Fushimi Inari Taisha shrine in Kyoto, I ventured into recreating the mystic ambiance of its iconic Torii gates using Unreal Engine and After Effects. <b>Learn More...</b><p>    
</div>
  </div>
</div>

{#if showModal}
  <div class="modal" on:click={closeModal}>
    <div class="modal-content" style="background-image: url('../../images/background.png'); background-repeat: repeat;" on:click|stopPropagation>
      <!-- Project 1 Details -->
      {#if selectedProject === 'project1'}
      <div class="titre-desc">
        <h2>Brisée : An Animated Short</h2>
        <p><!-- Full description... --></p>
      </div>
        <!-- Embed the final short movie and additional videos/gifs -->
        <iframe src="https://drive.google.com/file/d/1zyteH3v9Dsi66w9EKvNre_D8iyt2ywji/view?usp=sharing" frameborder="0" allowfullscreen></iframe>
        <!-- ... -->
      {/if}

      <!-- Project 2 Details -->
      {#if selectedProject === 'project2'}
      <div class="titre-desc">
        <h2>Tokyo Wagon</h2>
        <p>As part of my venture into the realms of 3D modeling, I embarked on a project to bring a train wagon from a drawing reference to life. The journey commenced with intricately modeling the wagon, ensuring every curve and edge resonated with the essence of the reference. Following the sculpting phase, I delved into the realms of shading, texturing, and lighting which truly breathed life into the model. The transition from a monochrome model to a textured masterpiece showcased the remarkable difference texturing makes. Below, you'll find the before and after texturing images along with the initial drawing reference that was the genesis of this creation. Through this project, not only did I refine my skills, but also appreciated the magic that lies in the details, making the inanimate, animate.</p>
        </div>
        <!-- Embed the final short movie and additional videos/gifs -->
        <div class="wagon-img">
          <h4>Reference</h4>
          <img src="../../images/ref.png" alt="ref">
          </div>
        <div class="wagon">
          <div class="wagon-img">
          <h4>After</h4>
          <img src="../../images/before-wagon.png" alt="before-wagon">
          </div>
          <div class="wagon-img">
          <h4>After</h4>
          <img src="../../images/after-wagon.png" alt="after-wagon">
          </div>
        
        </div>
        <!-- ... -->
      {/if}
      <!-- Project 3 Details -->
      {#if selectedProject === 'project3'}
      <div class="titre-desc">
        <h2>Fushimi Inari Taisha shrine - Unreal Engine</h2>
        <p>Inspired by the peaceful nights at the Fushimi Inari Taisha shrine in Kyoto, I ventured into recreating the mystic ambiance of its iconic Torii gates using Unreal Engine and After Effects. The resulting video portrays a tranquil night scene, enveloped in gentle rain and a soft haze of fog amidst the vermilion gates. This project was a passage into the realms of environmental design and visual storytelling, where each frame is a blend of 3D artistry and the spiritual essence of the ancient shrine, transporting the viewer through a visually soothing journey amidst the quiet rain in a sacred, timeless space.</p>
        </div>
        <!-- Embed the final short movie and additional videos/gifs -->
        <iframe src="https://drive.google.com/file/d/1Xjx3Fi4nxWlCIwK2PrbYDsLfYdw7QHmD/view?usp=sharing" frameborder="0" allowfullscreen></iframe>
        <!-- ... -->
      {/if}
    </div>
  </div>
{/if}
</div>
