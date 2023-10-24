<script>
import AboutMe from './AboutMe.svelte'; /* Import the AboutMe component */
  // Svelte Component Script
  let imageCards1 = [
    {
      title: 'Photography',
      description: 'Description for Image 1',
      link: '/photography',
      imgSrc: '../images/photography.png',
      alt: 'Description of Image 1'
    },
    {
      title: 'Design',
      description: 'Description for Image 2',
      link: '/design',
      imgSrc: '../images/design.png',
      alt: 'Description of Image 2'
    },];
let imageCards2 = [
    {
      title: 'Videography',
      description: 'Description for Image 3',
      link: '/video',
      imgSrc: '../images/video.png',
      alt: 'Description of Image 3'
    },
{
      title: '3D Art',
      description: 'Description for Image 4',
      link: '/3dart',
      imgSrc: '../images/3dart.png',
      alt: 'Description of Image 4'
    },];
let imageCards3 = [
    {
      title: 'Coding',
      description: 'Description for Image 5',
      link: '/coding',
      imgSrc: '../images/coding.png',
      alt: 'Description of Image 5'
    },];


  function navigateTo(link) {
    window.location.href = link;
  }
</script>

<div class="index">

  <div class="banner">
    <img src="../images/banner.png" alt="Banner Description" class="banner-image">
  </div>
<div class="banner-phone">
    <img src="../images/banner-phone.png" alt="Banner Description" class="banner-image">
  </div>
<AboutMe />
<div class="title-container">
    <h2 class="title-text">My Projects</h2>
</div>

  <div class="image-row">
    {#each imageCards1 as { title, description, link, imgSrc, alt } (title)}
      <div class="image-card" on:click={() => navigateTo(link)}>
        <img src={imgSrc} alt={alt}>
        <div>
          <h4>{title}</h4>
          <p>{description}</p>
        </div>
      </div>
    {/each}
  </div>
<div class="image-row">
    {#each imageCards2 as { title, description, link, imgSrc, alt } (title)}
      <div class="image-card" on:click={() => navigateTo(link)}>
        <img src={imgSrc} alt={alt}>
        <div>
          <h4>{title}</h4>
          <p>{description}</p>
        </div>
      </div>
    {/each}
  </div>
<div class="image-row">
    {#each imageCards3 as { title, description, link, imgSrc, alt } (title)}
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
