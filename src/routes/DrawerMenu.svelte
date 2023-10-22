<script>
    import { onMount } from 'svelte';
    let menuOpen = false;

    /* New function to close the menu */
    function closeMenu() {
        menuOpen = false;
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
<!-- Mobile menu -->
<nav class="nav-mobile">
    <button class="menu-toggle" on:click={() => menuOpen = !menuOpen}>
        ☰ <!-- This is your menu icon -->
    </button>
    <div class={menuOpen ? 'mobile-menu-open open' : 'mobile-menu-open'}>
        <button on:click={closeMenu}>X</button> <!-- This is your close button -->
        <ul>
            <!-- Add your menu items here, similar to the desktop version but with the closeMenu function on click -->
            <li on:click={closeMenu}><a href="/" class:active={$currentPage === '/'}>Home</a></li>
            <!-- ... other menu items ... -->
        </ul>
    </div>
</nav>
