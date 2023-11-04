<script>
import AboutMe from './AboutMe.svelte'; /* Import the AboutMe component */
  // Svelte Component Script
  let imageCards1 = [
    {
      title: 'Photography',
      description: '',
      link: '/photography',
      imgSrc: '../images/photography.png',
      alt: 'Photography'
    },
    {
      title: '3D Art',
      description: '',
      link: '/3dart',
      imgSrc: '../images/3dart.png',
      alt: '3dart'
    },];
let imageCards2 = [
{
      title: 'Design',
      description: '',
      link: '/design',
      imgSrc: '../images/design.png',
      alt: 'Design'
    },
{
      title: 'Coding',
      description: '',
      link: '/Coding',
      imgSrc: '../images/coding.png',
      alt: 'Web Devlopement'
    },];

  function navigateTo(link) {
    window.location.href = link;
  }
</script>

<div class="index">

  <div class="banner">
    <img src="../images/banner-noise.png" alt="Banner Description" class="banner-image">
  </div>
<div class="banner-phone">
    <img src="../images/banner-phone-noise.png" alt="Banner Description" class="banner-image">
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
<div class="image-row" style="padding-bottom:3rem;">
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
</div>
