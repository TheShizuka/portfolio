<script>
  import { onMount } from 'svelte';
  import '../Styles/styles.css';
  import DrawerMenu from './DrawerMenu.svelte'; /* Import the DrawerMenu component */
let menuOpen = false;
</script>

<header>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Shizuka's Portfolio</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Tilt+Neon&display=swap" rel="stylesheet">
<button class="menu-toggle" on:click={() => menuOpen = !menuOpen}>
    ☰
  </button>
  <div class="header">
    <DrawerMenu /> <!-- Use the DrawerMenu component -->
  </div>
</header>

<main>
  <slot />
</main>
