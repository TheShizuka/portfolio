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
    flex-direction: row;
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
    <img src="../../images/brisee.png" alt="brisée">
    <div class="text">
      <h3>Brisée - An Animated Short</h3>
      <p>During my time learning 3D graphics, I worked with three others on a short film called "Brisée" wich means shattered in French. Our story happens in a trashcan, where a forgotten shattered porcelain doll named Elisabeth finds a friend among the garbage. </p>
      <p style="padding-top: 2rem;"><b>Learn More...</b></p> 
    </div>
  </div>

  <!-- Project 2 -->
  <div class="project reverse project2" on:click={() => openModal('project2')}>
    <img src="../../images/wagon+ref.png" alt="wagon">
    <div class="text">
      <h3>Tokyo Wagon</h3>
      <p>In this project, I took on the challenge of creating a 3D model of a train wagon based on a drawing reference.</p>
      <p style="padding-top: 2rem;"><b>Learn More...</b></p> 
    </div>
  </div>


<!-- Project 3 -->
  <div class="project project3" on:click={() => openModal('project3')}>
    <img src="../../images/inari.png" alt="inari">
    <div class="text">
      <h3>Fushimi Inari Taisha shrine - Unreal Engine</h3>
      <p>Inspired by the peaceful nights at the Fushimi Inari Taisha shrine in Kyoto, I ventured into recreating the mystic ambiance of its iconic Torii gates using Unreal Engine and After Effects. </p>  
        <p style="padding-top: 2rem;"><b>Learn More...</b></p> 
      </div>
      </div>

   <!-- Project 4 -->
  <div class="project reverse project4" on:click={() => openModal('project4')}>
    <img src="../../images/sub.png" alt="substance">
    <div class="text">
      <h3>Substance Painter and Designer</h3>
      <p>In a quest to broaden my material creation skills, I undertook a project focusing on two distinct materials.</p>
      <p style="padding-top: 2rem;"><b>Learn More...</b></p> 
    </div>
  </div>

  <!-- Project 5 -->
  <div class="project project5" on:click={() => openModal('project5')}>
    <img src="../../images/bg+ref.webp" alt="bg">
    <div class="text">
      <h3>Hard Surface - Toko Biscuit</h3>
      <p>Taking inspiration from a drawing, I worked on modeling a street food restaurant by a lake with a miniature city. This project was all about capturing the details from the drawing into the 3D model.</p>  
        <p style="padding-top: 2rem;"><b>Learn More...</b></p> 
      </div>
      </div>

<!-- Project 6 -->
  <div class="project reverse project6" on:click={() => openModal('project6')}>
    <img src="../../images/zbrush.png" alt="zbrush">
    <div class="text">
      <h3>Anatomy - ZBrush</h3>
      <p>Engaging in anatomy studies using ZBrush, I delved into crafting a detailed head, a muscular torso, and a facial cube.</p>
      <p style="padding-top: 2rem;"><b>Learn More...</b></p> 
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
        <h2>Brisée - An Animated Short</h2>
        <p>During my time learning 3D graphics, I worked with three others on a short film called "Brisée" wich means shattered in French.  Our story happens in a trashcan, where a forgotten shattered porcelain doll named Elisabeth finds a friend among the garbage.

In our group, we all had different jobs. I was in charge of rigging, making sure the main characters could move properly in our scenes. I also worked on rendering, which is important for putting everything together later on. Besides, I helped with some parts of compositing and video editing to keep the story flowing well on screen.

I was the "go-to person" for solving problems in our group. I fixed issues in texturing and animation, how characters looked and moved, helping keep our project on track.

Below, you'll see our final version of "Brisée," along with some examples of the work I did. Through "Brisée," we didn’t just tell a sad story, we also learned a lot about working together and dealing with common challenges in 3D animation.</p>
      
        <!-- Embed the final short movie and additional videos/gifs -->
        <h4>Final Result</h4>
        <div class="video-container">
                    <video controls poster="../../images/brisee.webp">
                        <source src="../../images/brisée.mp4" type="video/mp4">
                        Your browser does not support the video tag.
                    </video>
                </div>
        </div>
        <div class="wagon-img">
          <h4>Characters</h4>
          </div>
        <div class="wagon">
          <div class="wagon-img">
          <img src="../../images/elis.png" alt="before-wagon">
          </div>
          <div class="wagon-img">
          <img src="../../images/charger.png" alt="after-wagon">
          </div>
        </div>
          <div class="wagon">
            <div class="wagon-img">
            <h4>Elisabeth Rig</h4>
        <div class="video-container">
            <video width="560" height="315" controls>
            <source src="../../images/elis.mp4" type="video/mp4">
              Your browser does not support the video tag.
            </video>
            </div>
            </div>
            <div class="wagon-img">
            <h4>Charger Rig</h4>
        <div class="video-container">
            <video width="560" height="315" controls>
            <source src="../../images/charger.mp4" type="video/mp4">
              Your browser does not support the video tag.
            </video>
            </div>
            </div>
          </div>
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
          <h4>Shading & Lighting</h4>
          <img src="../../images/before-wagon.png" alt="before-wagon">
          </div>
          <div class="wagon-img">
          <h4>Texturing</h4>
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
        
        <!-- Embed the final short movie and additional videos/gifs -->
<div class="video-container">
        <video width="1120" height="630" controls poster="../../images/fond.png">
        <source src="../../images/ue-tori.mp4" type="video/mp4">
          Your browser does not support the video tag.
        </video>
        </div>
        </div>
        <!-- ... -->
      {/if}

<!-- Project 4 Details -->
      {#if selectedProject === 'project4'}
      <div class="titre-desc">
        <h2>Viking Shielf & Floor Material</h2>
        <p>In a quest to broaden my material creation skills, I undertook a project focusing on two distinct materials. The first, a meticulous depiction of a Viking shield for a video game, was crafted using Substance Painter, encapsulating a blend of historical authenticity and artistic aesthetic. The second venture involved devising a procedural material for floor tiles using Substance Designer, showcasing a blend of technical prowess and artistic vision. These endeavors not only honed my expertise in material design but also reflected the versatility and depth of knowledge I've acquired through various software tools.</p>
        </div>
        <!-- Embed the final short movie and additional videos/gifs -->
        <div class="wagon">
          <div class="wagon-img">
          <h4>Viking Shield</h4>
          <img src="../../images/shield.webp" alt="before-wagon">
          </div>
          <div class="wagon-img">
          <h4>Floor Tiles</h4>
          <img src="../../images/tiles.webp" alt="after-wagon">
          </div>
        
        </div>
        <!-- ... -->
      {/if}

<!-- Project 5 Details -->
      {#if selectedProject === 'project5'}
      <div class="titre-desc">
        <h2>Hard Surface - Toko Biscuit</h2>
        <p>Taking inspiration from a drawing, I worked on modeling a street food restaurant by a lake with a miniature city. This project was all about capturing the details from the drawing into the 3D model. Although I didn't venture into texturing, I added some basic lighting to enhance the scene. This task was a great practice in hard surface modeling, helping me focus on getting the structure and details right while also playing with light to create a pleasant scene.</p>
        </div>
        <!-- Embed the final short movie and additional videos/gifs -->
        <div class="wagon">
          <div class="wagon-img">
          <h4>Reference</h4>
          <img src="../../images/bg-ref.webp" alt="before-wagon">
          </div>
          <div class="wagon-img">
          <h4>Modelisation</h4>
          <img src="../../images/bg.webp" alt="after-wagon">
          </div>
        
        </div>
        <!-- ... -->
      {/if}
<!-- Project 6 Details -->
      {#if selectedProject === 'project6'}
      <div class="titre-desc">
        <h2>Anatomy - ZBrush</h2>
        <p>Engaging in anatomy studies using ZBrush, I delved into crafting a detailed head, a muscular torso, and a facial cube. The cube was particularly interesting as each of its sides featured a different facial part - eyes, nose, ear, and mouth. This unique approach allowed me to focus on the anatomy of each facial element separately, honing my skills in a targeted manner. Through recreating and studying these anatomical structures, I was able to deepen my understanding, refine my sculpting techniques, and further my proficiency in ZBrush, making each study an enriching learning experience.</p>
        </div>
        <!-- Embed the final short movie and additional videos/gifs -->
        <div class="wagon-img">
            <h4>Cube Face</h4>
          <img src="../../images/face.gif " alt="face">
          </div>
        </div>
        <div class="wagon">
          <div class="wagon-img">
          <h4>Head</h4>
          <img src="../../images/head.gif" alt="head">
          </div>
          <div class="wagon-img">
          <h4>Torso</h4>
          <img src="../../images/torso.gif" alt="torso.gif">
          </div>
        
        </div>
        <!-- ... -->
      {/if}








    </div>
  </div>
{/if}
</div>
