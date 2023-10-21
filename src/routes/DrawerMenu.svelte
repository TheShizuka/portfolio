<script>
  import { onMount } from 'svelte';

  let menuOpen = false;

  onMount(() => {
    const links = document.querySelectorAll('.menu a');
    links.forEach(link => {
      link.addEventListener('click', () => {
        links.forEach(link => link.parentElement.classList.remove('active'));
        link.parentElement.classList.add('active');
      });
    });
  });
</script>

<nav class="nav">
  <button class="menu-toggle" on:click={() => menuOpen = !menuOpen}>
    ☰
  </button>
  <div class={menuOpen ? 'menu-container open' : 'menu-container'}>
    <ul class="menu">
      <li class="active"><a href="/">Home</a></li>
      <li><a href="/design">Design</a></li>
      <li><a href="/coding">Coding Projects</a></li>
      <li><a href="/3d-art">3D Content</a></li>
      <li><a href="/photography">Photography</a></li>
      <li><a href="/video">Videography</a></li>
    </ul>
  </div>
</nav>
