<script>
  // Add any Svelte-specific code or import statements here
</script>

<style>
  .about-section {
    display: grid;
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

  .skills {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
  }

  .skill {
    background: #f4f4f4;
    padding: 5px 10px;
    border-radius: 5px;
    display: flex;
    align-items: center;
    gap: 5px;
  }

  @media (max-width: 768px) {
    .about-section {
      grid-template-columns: 1fr;
    }
  }
</style>

<div class="about-section">
  <div>
    <img src="path_to_your_image.jpg" alt="Hicham's Image" />
  </div>

  <div>
    <h2>About Hicham</h2>
    <p>
      Hello! I'm Hicham Ayat, a versatile digital creator with a passion for blending the worlds of art and technology. From video and photo editing to 3D modeling and web development, my diverse skill set allows me to bring innovative visions to life. With a background spanning multiple countries and a keen interest in both pop and traditional aspects of Japanese culture, I bring a unique perspective to every project I undertake.
    </p>

    <h3>Skills Snapshot:</h3>
    <div class="skills">
      <div class="skill">
        <img src="path_to_digital_creation_icon.png" alt="Digital Creation Icon" />
        Digital Creation
      </div>
      <div class="skill">
        <img src="path_to_3d_artistry_icon.png" alt="3D Artistry Icon" />
        3D Artistry
      </div>
      <div class="skill">
        <img src="path_to_web_development_icon.png" alt="Web Development Icon" />
        Web Development
      </div>
      <div class="skill">
        <img src="path_to_design_and_animation_icon.png" alt="Design & Animation Icon" />
        Design & Animation
      </div>
      <div class="skill">
        <img src="path_to_languages_icon.png" alt="Languages Icon" />
        Languages
      </div>
    </div>
    
    <!-- You can continue with the rest of the sections, following the structure outlined above. -->
  </div>
</div>
