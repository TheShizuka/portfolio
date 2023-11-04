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
  <h2>My Coding Odyssey</h2>
  <p>Having self-taught coding, I’ve tackled various projects for fun, friends, and university. Each endeavor has honed my skills and fueled my passion for technology. This page showcases a range of projects reflecting my growing expertise and enthusiasm. Through each line of code, I've embraced learning and look forward to more exciting challenges ahead.</p>
</div>
<div class="page">
<div class="project-container">
  <!-- Project 1 -->
  <div class="project project1" on:click={() => openModal('project1')}>
    <video autoplay muted loop style="height: 300px;">
    <source src="../../images/hype-train.mp4" type="video/mp4">
    Your browser does not support the video tag.
    </video>
    <div class="text">
      <h3>Twitch Custom Hype Train</h3>
      <p>Embarking on a project to create a custom Twitch Hype Train for a friend's subathon, integrating Streamlabs and KOFI APIs to trigger the train on every donation, sub, resub, follow, and bits received on the stream.</p>
      <p style="padding-top: 2rem;"><b>Learn More...</b></p> 
    </div>
  </div>

  <!-- Project 2 -->
  <div class="project reverse project2" on:click={() => openModal('project2')}>
    <img src="../../images/discord-bot.png" alt="discord-bot">
    <div class="text">
      <h3>Discord Bot</h3>
      <p>Embarking on a Node.js learning venture led me to create a Discord bot, blending humor and utility.</p>
      <p style="padding-top: 2rem;"><b>Learn More...</b></p> 
    </div>
  </div>


<!-- Project 3 -->
  <div class="project project3" on:click={() => openModal('project3')}>
    <img src="../../images/mmt.png" alt="mmt">
    <div class="text">
      <h3>Meet My Tempo</h3>
      <p>In a university project, our team created "Meet My Tempo" (MMT), a platform for musicians to share their tunes, much like an Instagram for music.</p>  
        <p style="padding-top: 2rem;"><b>Learn More...</b></p> 
      </div>
      </div>

<h4 style="color:white;">Lastly this website has been coded by me and you can also check it on Github <a href="https://github.com/TheShizuka/portfolio" target="_blank">here</a></h4>



</div>

{#if showModal}
  <div class="modal" on:click={closeModal}>
    <div class="modal-content" style="background-image: url('../../images/background.png'); background-repeat: repeat;" on:click|stopPropagation>
    <button class="close-button" style="background-image: url('../../images/background.png'); background-repeat: repeat;" on:click={closeModal}>&times;</button>
      <!-- Project 1 Details -->
      {#if selectedProject === 'project1'}
      <div class="titre-desc">
        <h2>Twitch Custom Hype Train</h2>
        <p>Embarking on a project to create a custom Twitch Hype Train for a friend's subathon, integrating Streamlabs and KOFI APIs to trigger the train on every donation, sub, resub, follow, and bits received on the stream.  I built the logic with JavaScript, added animation with CSS, and crafted Minecraft-inspired assets with photoshop. To display the train, the streamer simply adds a browser source link in OBS using the StreamLabs socket. This project sharpened my skills in handling GET and POST requests, and managing a socket.io server, all while navigating the Streamlabs API to bring the Hype Train to life in under a month. The train can be 100% customised, for now it's just a personal project but maybe in the future it will be released to the public.</p>
      
        <!-- Embed the final short movie and additional videos/gifs -->
        <h4>Final Result</h4>
        <div class="video-container">
                    <video autoplay muted loop>
                    <source src="../../images/hype-train.mp4" type="video/mp4">
                    Your browser does not support the video tag.
                    </video>
                </div>
        </div>
        <div class="wagon-img">
          <h4>Assets</h4>
          </div>
        <div class="wagon">
          <div class="wagon-img">
          <img src="../../images/train.png" alt="main-wagon">
          </div>
          <div class="wagon-img">
          <img src="../../images/car5.png" alt="wagon">
          </div>
        </div>
        <!-- ... -->
      {/if}

      <!-- Project 2 Details -->
      {#if selectedProject === 'project2'}
      <div class="titre-desc">
        <h2>Discord Bot</h2>
        <p>Embarking on a Node.js learning venture led me to create a Discord bot, blending humor and utility. The bot started with amusing interactions, responding to "!hello" and sharing random cat images on "!cat" thanks to a cat API. The quest for complexity drove me to integrate the Riot Games API, enabling my bot to fetch and display League of Legends player data with "!Stats player name", and offer champion history and matchup tips on "!champion champion name". This project was not only a technical exploration but also a fun dive into enhancing gaming interactions.</p>
        </div>
        <!-- Embed the final short movie and additional videos/gifs -->
        <div class="wagon-img">
          <h4>hl!Hello</h4>
          <img src="../../images/hello.png" alt="hello">
          </div>
        <div class="wagon-img">
          <h4>hl!Stats</h4>
          <img src="../../images/stats.png" alt="stats">
          </div>
      
        <!-- ... -->
      {/if}
      <!-- Project 3 Details -->
      {#if selectedProject === 'project3'}
      <div class="titre-desc">
        <h2>Meet My Tempo</h2>
        <p>In a university project, our team created "Meet My Tempo" (MMT), a platform for musicians to share their tunes, much like an Instagram for music. While my teammates handled the marketing and business side, I took on the design and coding tasks using Vue.js, PHP, SQL, HTML, CSS, and JS. I developed a secure login system, search and music upload features, and designed various pages like the homepage, profile pages, and a private messaging section. Through MMT, I got a hands-on experience in front and back-end development while creating a fun space for musicians to connect.</p>
        
        <!-- Embed the final short movie and additional videos/gifs -->
<div class="wagon-img">
          <h4>You can check the project on Github <a href="https://github.com/TheShizuka/MeetMyTempo" target="_blank">here</a></h4>
          </div>
<div class="wagon-img">
          <h4>Example</h4>
          </div>
        <div class="wagon">
          <div class="wagon-img">
          <img src="../../images/mmt.png" alt="main-wagon">
          </div>
          <div class="wagon-img">
          <img src="../../images/mmt1.png" alt="wagon">
          </div>
          <div class="wagon-img">
          <img src="../../images/mmt2.png" alt="wagon">
          </div>
          </div>
        </div>
        <!-- ... -->
      {/if}






    </div>
  </div>
{/if}
</div>
