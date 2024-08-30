<script>
  import { onMount } from 'svelte';

  let isMenuOpen = false;
  let isDarkMode = true;
  let isScrolled = false;

  // Toggle burger menu
  function toggleMenu() {
    isMenuOpen = !isMenuOpen;
    if (isMenuOpen) {
      document.body.classList.add('menu-open');
    } else {
      document.body.classList.remove('menu-open');
    }
  }

  // Toggle dark mode
  function toggleDarkMode() {
    isDarkMode = !isDarkMode;
    document.body.classList.toggle('dark-mode', isDarkMode);
  }

  // Handle scroll event
  onMount(() => {
    const threshold = 10;
    const handleScroll = () => {
      isScrolled = window.scrollY > threshold;
    };

    window.addEventListener('scroll', handleScroll);

    return () => {
      window.removeEventListener('scroll', handleScroll);
    };
  });
</script>

<!-- Header Component -->
<header class:scrolled={isScrolled}>
  <nav>
    <div class="logo">
      <a href="#hero">
        <h3 class="header__logo">Jukulyn'sFinest </h3>
      </a>
    </div>

    <ul class="header__nav-menuDesktop">
      <li class="header__nav-linkDesktop"><a href="#hero">Home</a></li>
      <li class="header__nav-linkDesktop"><a href="#about">About</a></li>
      <li class="header__nav-linkDesktop"><a href="#services">Services</a></li>
      <li class="header__nav-linkDesktop"><a href="#pricings">Pricings</a></li>
      <li class="header__nav-linkDesktop"><a href="#contact">Contact</a></li>
    </ul>

    <!-- Burger Menu -->
    <ul class="header__nav-menu" class:open={isMenuOpen}>
      <li class="header__nav-link"><a href="#hero" on:click={toggleMenu}>Home</a></li>
      <li class="header__nav-link"><a href="#about" on:click={toggleMenu}>About</a></li>
      <li class="header__nav-link"><a href="#services" on:click={toggleMenu}>Services</a></li>
      <li class="header__nav-link"><a href="#pricings" on:click={toggleMenu}>Pricings</a></li>
      <li class="header__nav-link"><a href="#contact" on:click={toggleMenu}>Contact</a></li>
    </ul>
    
    <div class="header__socials">
      <a href="https://www.facebook.com/jukulynsfinest" target="_blank">
        <i class="fa-brands fa-facebook"></i>
      </a>
      <a href="https://www.youtube.com/@jukulynsfinest2238" target="_blank">
        <i class="fa-brands fa-youtube"></i>
      </a>
      <a href="https://www.tiktok.com/@jukulynsfinest?lang=en" target="_blank">
        <i class="fa-brands fa-tiktok"></i>
      </a>
      <a href="https://www.instagram.com/jukulynsfinest/" target="_blank">
        <i class="fa-brands fa-instagram"></i>
      </a>

    </div>
    <!-- Dark Mode Toggle -->
    <!-- <div class="darkLight" on:click={toggleDarkMode}>
      <i class={isDarkMode ? "fa-solid fa-sun" : "fa-solid fa-moon"}></i>
    </div> -->

    <!-- Burger Icon Toggle -->
    <div class="menu-toggle">
      <button  on:click={toggleMenu}>
        <i class={isMenuOpen ? "fa-solid fa-xmark" : "fa-solid fa-bars"}></i>
      </button>
    </div> 
  </nav>
</header>

<style>
  /* Mobile First Styles */
  header {
    height: 11vh;
    width: 100%;
    position: fixed;
    top: 0;
    left: 50%;
    transform: translateX(-50%);
    padding: 1rem 2rem;
    z-index: 1000;
    transition: background .3s ease, backdrop-filter .3s ease ;
  }

  header.scrolled {
    background: rgba(22, 22, 22, .5);
    backdrop-filter: blur(10px);
    border-bottom: 1px dotted rgba(22, 22, 22, .4);
  }

  nav {
    display: flex;
    align-items: center;
    justify-content: space-between;
    position: relative;
  }

  .header__nav-menuDesktop{
    display: none;
  }
  
  .logo {
    font-size: .5rem;

  }

  .header__socials{
    display: flex;
    gap: 1rem;
    align-items: center;
    justify-content: center;
    font-size: var(--size-xs);
  }

  /* Burger Menu Styles */
  .header__nav-menu {
    position: fixed;
    top: 0;
    right: 0;
    height: 100vh;
    width: 70%;
    max-width: 300px;
    background: rgba(22, 22, 22, 1);
    transform: translateX(100%);
    transition: transform 0.3s ease;
    padding-top: 4rem;
    z-index: 999;
    display: flex;
    flex-direction: column;
    
    align-items: center;
    gap: 1.5rem;
  }
  

  .header__nav-menu.open {
    transform: translateX(0);
  }

  /* Nav Links */
  .header__nav-link {
    font-size: 1rem;
    text-transform: uppercase;
  
    transform: translateY(600%);
  }

  .header__nav-link a {
    text-decoration: none;
    color: white;
    transition: color 0.3s;
  }

 

  /* Dark Mode Toggle */
  /* .darkLight {
    cursor: pointer;
  }

  .darkLight i {
    color: white;
    font-size: 1.5rem;
  } */

  /* Burger Icon */
  .menu-toggle {
    cursor: pointer;
    z-index: 1001;
  }

  .menu-toggle i {
    font-size: 1.2rem;
    color: white;
  }

  /* Background overlay when menu is open */
  /* .menu-open body {
    background: rgba(22, 22, 22, .5);
    backdrop-filter: blur(10px);
    overflow: hidden; 
  } */

  /* Medium screens and up */
  @media (min-width: 640px) {
    .header__nav-menu {
      transform: translateX(100%);
    }

    .header__nav-menu.open {
      transform: translateX(0);
    }

    .header__nav-link {
      font-size: 1.2rem;
    }

    /* .darkLight i, .menu-toggle i {
      font-size: 1.8rem;
    } */
  }

  /* Large screens and up */
  @media (min-width: 768px) {

    nav{
      margin-top: 1rem;
    }

    .logo{
      font-size: var(--size-base);
    }
  }

  /* Extra large screens */
  @media (min-width: 1024px) {

    .header__nav-linkDesktop {
      font-size: .8rem;
    }

    .header__nav-menuDesktop{
      display: flex;
      align-items: center;
      gap: 2rem;
      text-transform: uppercase;
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);

    }

    .header__nav-linkDesktop {
      position: relative;
      display: inline-block;
    }

    .header__nav-linkDesktop::after {
      content: '';
      position: absolute;
      width: 0;
      height: 1px;
      bottom: -2px; 
      left: 50%;
      background-color: white; 
      transform: translateX(-50%);
      transition: width 0.3s ease;
    }

    .header__nav-linkDesktop:hover::after {
      width: 100%;
    }

   

    /* .header__nav-menu {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      align-items: center;
      justify-content: space-between;
      height: auto;
      width: auto;
      flex-direction: row;
      background: none;
      padding-top: 0;
      z-index: auto;
      display: flex;
      display: none;
    } */

   .logo, .header__socials,.header__nav-linkDesktop{
    align-items: center;
    justify-content: center;
    vertical-align: middle;
    margin-top: auto;
    margin-bottom: auto;
    transform: translateY(-50%);
   }

   .logo{
    font-size: .8rem;
   }
  
    .menu-toggle{
      display: none;
    }

    /* .darkLight i {
      font-size: 2rem;
    } */
  }
</style>
