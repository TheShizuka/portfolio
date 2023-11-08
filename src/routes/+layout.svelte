<script>
  import { onMount } from 'svelte';
  import '../Styles/styles.css';
  import DrawerMenu from './DrawerMenu.svelte';
  import Footer from './Footer.svelte';
  import Analytics from '$lib/analytics.svelte'
</script>

<header>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Shizuka's Portfolio</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Roboto&display=swap" rel="stylesheet">

  <div class="header" style="background-image: url('../../images/background.png'); background-repeat: repeat;">
    <DrawerMenu /> <!-- Use the DrawerMenu component -->
  </div>
</header>

<main>
  <Analytics />
  <slot />

<Footer />
</main>

