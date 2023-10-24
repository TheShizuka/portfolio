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
    width: 96px;
    height: 96px;
  }

  .skills-section {
    margin-top: 20px;
  }
.skill-card {
    display: flex;
    gap: 20px;
    align-items: center;
    border: 1px solid #e0e0e0;
    padding: 10px 20px;
    border-radius: 10px;
    margin-bottom: 20px;
  }
.skill-logos {
    display: flex;
    gap: 10px;
    align-items: center;
  }
.about-me-text{
margin-bottom:5rem;
}

  @media (max-width: 768px) {
    .about-section {
      grid-template-columns: 1fr;
    }
  }
</style>

<div class="about-section">
  <div>
    <h2>Learn more about me...</h2>
    <p class="about-me-text">
      Hello! I'm Hicham Ayat, a versatile digital creator with a passion for blending the worlds of art and technology. From video and photo editing to 3D modeling and web development, my diverse skill set allows me to bring innovative visions to life. With a background spanning multiple countries and a keen interest in both pop and traditional aspects of Japanese culture, I bring a unique perspective to every project I undertake.
    </p>

    <h3>Skills Snapshot:</h3>
    <div class="skills-section">
      <div class="skill-card">
        <h3>3D Artistry</h3>
        <div class="skill-logos">
          <img src="path_to_MAYA_Autodesk_icon.png" alt="MAYA Autodesk Icon" />
          <img src="path_to_ZBrush_icon.png" alt="ZBrush Icon" />
          <!-- Add other 3D Artistry logos here -->
        </div>
      </div>

      <div class="skill-card">
        <h3>Web Development</h3>
        <div class="skill-logos">
          <img src="path_to_HTML_icon.png" alt="HTML Icon" />
          <img src="path_to_CSS_icon.png" alt="CSS Icon" />
          <!-- Add other Web Development logos here -->
        </div>
      </div>

      <div class="skill-card">
        <h3>Digital Creation</h3>
        <div class="skill-logos">
          <img src="path_to_Photoshop_icon.png" alt="Photoshop Icon" />
          <img src="path_to_PremierePro_icon.png" alt="Premiere Pro Icon" />
          <!-- Add other Digital Creation logos here -->
        </div>
      </div>

      <!-- You can continue adding other skill categories in the same format -->

    </div>
    
    <!-- You can continue with the rest of the sections, following the structure outlined above. -->
  </div>
</div>
