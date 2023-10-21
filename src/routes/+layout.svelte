<script>
  import { onMount } from 'svelte';
  import '../Styles/styles.css';
  import DrawerMenu from './DrawerMenu.svelte';

  let lastScrollTop = 0;
  let headerHide = false;
  let headerElement;

  onMount(() => {
    headerElement = document.querySelector('.header');

    window.addEventListener('scroll', () => {
      let scrollTop = window.pageYOffset || document.documentElement.scrollTop;
      headerHide = scrollTop > lastScrollTop;
      lastScrollTop = scrollTop;
    });
  });

  $: {
    if (headerElement) {
      if (headerHide && window.innerWidth > 768) {  // Header hide on scroll only in PC version
        headerElement.classList.add('header-hide');
      } else {
        headerElement.classList.remove('header-hide');
      }
    }
  }
</script>

<header class="header">
  <DrawerMenu /> <!-- Use the DrawerMenu component -->
</header>

<main>
  <slot />
</main>
