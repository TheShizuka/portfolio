<script>
  import { onMount } from 'svelte';
  let menuOpen = false;

  function closeMenu() {
    menuOpen = false;
  }

  onMount(() => {
    // This ensures the script runs after the component is mounted on the client side.
    const links = document.querySelectorAll('.menu a');
    links.forEach(link => {
      link.addEventListener('click', () => {
        closeMenu(); // we close the menu when a link is clicked
        links.forEach(link => link.parentElement.classList.remove('active'));
        link.parentElement.classList.add('active');
      });
    });
  });
</script>

<!-- We keep one nav and manage visibility with CSS -->
<nav class="nav-mobile">
  <button class="menu-toggle" on:click={() => menuOpen = !menuOpen}>☰</button>
  <div class={menuOpen ? 'mobile-menu-open open' : 'mobile-menu-open'}>
    <button on:click={closeMenu}>X</button>
    <ul>
      <li on:click={closeMenu}><a href="/" class:active={$currentPage === '/'}>Home</a></li>
    <li><a href="/design">Design</a></li>
    <li><a href="/coding">Coding Projects</a></li>
    <li><a href="/3d-art">3D Content</a></li>
    <li><a href="/photography">Photography</a></li>
    <li><a href="/video">Videography</a></li>
</ul>
  </div>
</nav>
