<script>
  // Svelte Component Script
  let imageCards = [
    {
      title: 'Title 1',
      description: 'Description for Image 1',
      link: '#',
      imgSrc: '',
      alt: 'Description of Image 1'
    },
    {
      title: 'Title 2',
      description: 'Description for Image 2',
      link: '#',
      imgSrc: '',
      alt: 'Description of Image 2'
    },
    // ... Add more image card objects here
  ];

  function navigateTo(link) {
    window.location.href = link;
  }
</script>

<div class="index">

  <div class="banner">
    <img src="../images/banner.png" alt="Banner Description" class="banner-image">
  </div>

  <div class="about">
        <img src="" alt="Learn more about my photography skills">
		<div class="text-about">
		<h3>Shizuka</h3>
        <p>Passionate and versatile digital creator with a diverse skill set spanning video/photo editing, 3D
			modeling, 2D art, and web development. Proficient in Adobe Suite, including Photoshop,
			Illustrator, Premiere Pro, and After Effects. Eager to contribute to innovative projects with a keen
			interest in remote roles related to video/photo creation, web design, and 3D artistry. Committed
			to continuous learning and growth in the digital domain. In addition to my digital creation skills,
			I also possess coding expertise, enabling me to develop and implement technical solutions for
			various projects.
			</p>
		</div>
    </div>

  <div class="image-row">
    {#each imageCards as { title, description, link, imgSrc, alt } (title)}
      <div class="image-card" on:click={() => navigateTo(link)}>
        <img src={imgSrc} alt={alt}>
        <div>
          <h4>{title}</h4>
          <p>{description}</p>
        </div>
      </div>
    {/each}
  </div>
</div>
