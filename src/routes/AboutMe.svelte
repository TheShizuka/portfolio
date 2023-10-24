<script>
  // Add any Svelte-specific code or import statements here
</script>

<style>
  .about-section {
    grid-template-columns: 1fr 3fr;
    gap: 20px;
    max-width: 1200px;
    margin: 0 auto;
    padding: 40px 20px;
  }

  .about-section img {
    width: 70px;
    height: 70px;
    padding-right: 1rem;
    padding-bottom: 1rem;
    margin-bottom: 3rem;
  }

  .skills-section {
    margin-top: 20px;
  }
.skill-card {
    flex-direction: column; /* Ensure title and logos stack vertically */
    gap: 10px;
    align-items: start;
    border: 1px solid #e0e0e0;
    padding: 10px 20px;
    border-radius: 10px;
    margin-bottom: 20px;
    text-align: center;
  }
.skill-logos {
    gap: 10px;
    align-items: center;
    overflow-x: auto; /* Make it scrollable */
    white-space: nowrap; /* Prevent logos from wrapping */
  }
.skill-logos::-webkit-scrollbar {
    height: 8px;
  }
.skill-logos::-webkit-scrollbar-thumb {
    background: #ccc;
    border-radius: 4px;
  }

  .skill-logos::-webkit-scrollbar-track {
    background: #f4f4f4;
  }
.about-me-text{
margin-bottom:5rem;
}
.about-sec{
text-align: center;
}

  @media (max-width: 700px) {
    .about-section {
      grid-template-columns: 1fr;
    }
.skill-card {
      flex-direction: row; /* On larger screens, make them side by side */
      align-items: center;
    }
  }
</style>

<div class="about-section">
  <div class="about-sec">
    <h2>Learn more about me...</h2>
    <p class="about-me-text">
      Hello! I'm Hicham Ayat, a versatile digital creator with a passion for blending the worlds of art and technology. From video and photo editing to 3D modeling and web development, my diverse skill set allows me to bring innovative visions to life. With a background spanning multiple countries and a keen interest in both pop and traditional aspects of Japanese culture, I bring a unique perspective to every project I undertake.
    </p>

    <h3>My Skills</h3>
    <div class="skills-section">
      <div class="skill-card">
        <h4>3D Artistry</h4>
        <div class="skill-logos">
          <img src="../images/maya.png" alt="MAYA Autodesk Icon" />
          <img src="../images/zbrush.png" alt="ZBrush Icon" />
          <img src="../images/arnold.png" alt="Arnold 3D render" />
          <img src="../images/UE.png" alt="Unreal Engine" />
          <img src="../images/nuke.png" alt="Nuke" />
          <img src="../images/C4D.png" alt="Cinema 4D" />
          <img src="../images/subpaint.png" alt="Substance Painter" />
          <!-- Add other 3D Artistry logos here -->
        </div>
      </div>

      <div class="skill-card">
        <h4>Web Development</h4>
        <div class="skill-logos">
          <img src="../images/AE.png" alt="After Effects" />
          <img src="../images/Illustrator.png" alt="Illustrator" />
          <img src="../images/lightroom.png" alt="lightroom" />
          <img src="../images/Photoshop.png" alt="Photoshop" />
          <img src="../images/premiere.png" alt="premiere pro" />
          <img src="../images/indesign.png" alt="indesign" />
          <img src="../images/OBS.png" alt="OBS" />
          <img src="../images/xd.png" alt="adobe xd" />
          <!-- Add other Web Development logos here -->
        </div>
      </div>

      <div class="skill-card">
        <h4>Digital Creation</h4>
        <div class="skill-logos">
          <img src="../images/AE.png" alt="After Effects" />
          <img src="../images/Illustrator.png" alt="Illustrator" />
          <img src="../images/lightroom.png" alt="lightroom" />
          <img src="../images/Photoshop.png" alt="Photoshop" />
          <img src="../images/premiere.png" alt="premiere pro" />
          <img src="../images/indesign.png" alt="indesign" />
          <img src="../images/OBS.png" alt="OBS" />
          <img src="../images/xd.png" alt="adobe xd" />
          <!-- Add other Digital Creation logos here -->
        </div>
      </div>
       <div class="skill-card">
          <h4>Languages</h4>
          <div class="skill-logos">
            <img src="../images/english.png" alt="English" />
            <img src="../images/french.png" alt="French" />
            <img src="../images/spanish.png" alt="Spanish" />
            <!-- Add other Digital Creation logos here -->
        </div>
      </div>

      <!-- You can continue adding other skill categories in the same format -->

    </div>
    
    <!-- You can continue with the rest of the sections, following the structure outlined above. -->
  </div>
</div>
