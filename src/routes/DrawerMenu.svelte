<script>
  let menuOpen = false;
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

<style>
/* ... existing styles ... */

.nav {
  position: relative;
}

.menu-toggle {
  font-size: 2em;
  background: none;
  border: none;
  cursor: pointer;
  display: none; /* Hide button by default */
}

.menu {
  display: flex;
  flex-direction: row;
  list-style: none;
  padding: 0;
  margin: 0;
}

.menu li {
  margin-left: 15px;
}

/* Drawer Menu Styles */
@media (max-width: 768px) {
  .menu-toggle {
    display: block; /* Show button on mobile */
  }

  .menu {
    flex-direction: column;
    position: absolute;
    top: 100%;
    left: 0;
    background-color: #fff;
    width: 100%;
    border-top: 1px solid #ddd;
    display: none;
  }

  .menu.open {
    display: block;
  }
}

/* ... existing styles ... */
</style>
