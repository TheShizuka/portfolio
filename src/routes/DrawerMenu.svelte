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
onMount(() => {
    const links = document.querySelectorAll('.drawer-menu ul li a');
    links.forEach(link => {
        link.addEventListener('click', () => {
            links.forEach(link => link.parentElement.classList.remove('active'));  // Remove 'active' class from all menu items
            link.parentElement.classList.add('active');  // Add 'active' class to the clicked menu item
        });
    });
});
</script>
  

<nav class="nav">
   <div class="nav-header">
        <img src="../images/logo.png" alt="Shizuka's Portfolio" class="title-header">
        <button class="menu-toggle" on:click={() => menuOpen = !menuOpen}>
            ☰
        </button>
    </div>
  <ul class={menuOpen ? 'menu open' : 'menu'}>
    <li>
        <a href="/" style="margin: 0;">
            <img src="../images/logo.png" alt="Shizuka's Portfolio" class="pc-title">
        </a>
    </li>
    <li class="active"><a href="/">Home</a></li>
    <li><a href="/photography">Photography</a></li>
    <li><a href="/3dart">3D Art</a></li>
    <li><a href="/design">Design</a></li>
    <li><a href="/Coding">Coding Projects</a></li>
    <li><a href="/contact">Contact</a></li>
  </ul>
<!-- New drawer menu for mobile -->
    <div class={menuOpen ? 'drawer-menu open' : 'drawer-menu'}>
        <button class="close-button" on:click={closeMenu}>×</button> <!-- Close button -->
        <ul>
            <!-- The same menu items, but you can style them differently or add new ones -->
            <li on:click={closeMenu} class="active"><a href="/">Home</a></li>
            <li on:click={closeMenu}><a href="/photography">Photography</a></li>
            <li on:click={closeMenu}><a href="/3dart">3D Art</a></li>
            <li on:click={closeMenu}><a href="/design">Design</a></li>
            <li on:click={closeMenu}><a href="/Coding">Coding Projects</a></li>
            <li on:click={closeMenu}><a href="/contact">Contact</a></li>
        </ul>
    </div>
</nav>
