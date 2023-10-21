<script>
  import { onMount } from 'svelte';

  let menuOpen = false;
  
  // reactive statement that runs whenever window.location changes
  $: {
    const links = document.querySelectorAll('.menu a');
    links.forEach(link => {
      if (window.location.pathname === link.getAttribute('href')) {
        link.parentElement.classList.add('active');
      } else {
        link.parentElement.classList.remove('active');
      }
    });
  }

 onMount(() => {
    const links = document.querySelectorAll('.menu a');
    links.forEach(link => {
        link.addEventListener('click', () => {
            links.forEach(link => link.parentElement.classList.remove('active'));  // Remove 'active' class from all menu items
            link.parentElement.classList.add('active');  // Add 'active' class to the clicked menu item
        });
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
