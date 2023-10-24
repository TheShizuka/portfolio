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
      title: 'Design',
      description: '',
      link: '/design',
      imgSrc: '../images/design.png',
      alt: 'Design'
    },];
let imageCards2 = [
    {
      title: 'Videography',
      description: '',
      link: '/video',
      imgSrc: '../images/video.png',
      alt: 'Videography'
    },
{
      title: '3D Art',
      description: '',
      link: '/3dart',
      imgSrc: '../images/3dart.png',
      alt: '3D Art'
    },];
let imageCards3 = [
    {
      title: 'Web Devlopement',
      description: '',
      link: '/coding',
      imgSrc: '../images/coding.png',
      alt: 'Web Devlopement'
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
