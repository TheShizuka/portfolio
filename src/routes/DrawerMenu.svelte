<script>
  let menuOpen = false;
  import { onMount } from 'svelte';

  onMount(() => {
    const links = document.querySelectorAll('.menu a');
    links.forEach(link => {
      if (window.location.pathname === link.getAttribute('href')) {
        link.parentElement.classList.add('active');
      }
    });
  });
</script>

<nav class="nav">
  <button class="menu-toggle" on:click={() => menuOpen = !menuOpen}>
    ☰
  </button>
  <ul class={menuOpen ? 'menu open' : 'menu'}>
    <li class="active"><a href="/">Home</a></li>
    <li><a href="/design">Design</a></li>
    <li><a href="/coding">Coding Projects</a></li>
    <li><a href="/3d-art">3D Content</a></li>
    <li><a href="/photography">Photography</a></li>
    <li><a href="/video">Videography</a></li>
  </ul>
</nav>
