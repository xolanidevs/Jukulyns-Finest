<script>
  import { onMount } from 'svelte';

  /**
   * @type {HTMLVideoElement}
   */
  let videoElement;

  onMount(() => {
    if (videoElement) videoElement.play();
  });
</script>

<section id="hero" class="hero fade-in">
  <video 
    bind:this={videoElement} 
    class="hero__video active" 
    muted 
    loop
  >
    <source src="/Hero-Video 2.mp4" type="video/mp4">
  </video>
  
  <h1 class="hero__content-title container">Jukulyn's Finest.</h1>
  
  <div class="hero__content-container container">
    {#each ['photography', 'videography', 'content creation', 'editing', 'web services'] as service}
      <p class="hero__content-description">{service}</p>
    {/each}
  </div>
  
  <a href="#contact" class="hero-contact__btn">HIRE US</a>
  
  <a class="hero__scroll-down" href="#about">
    <i class="fa-solid fa-caret-down"></i>
  </a>
</section>

<style>
  .hero {
    width: 100%;
    height: 100vh;
    background: linear-gradient(#0b0b0b80, #0b0b0b80);
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    overflow: hidden;
    margin-top: 0;
  }

  .hero__video {
    position: absolute;
    inset: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
    z-index: -2;
  }

  .hero__content-title,
  .hero__content-container {
    font-family: 'Clash Display', sans-serif;
    text-transform: uppercase;
  }

  .hero__content-container {
    display: flex;
    
    gap: 1rem;
    align-items: center;
    justify-content: center;
    margin-top: 1rem;
  }

  .hero__content-title {
    font-size: 1.7rem;
    text-align: center;
    margin-top: 4rem;
  }

  .hero__content-description {
    font-size: .338rem;
    font-weight: 500;
    text-align: center;
    margin-bottom: 2rem;
  }

  .hero-contact__btn {
    margin: 2rem auto 0 auto;
    text-align: center;
    justify-content: center;
    border: 1px dotted var(--clr-light);
    color: var(--clr-light);
    font-weight: bold;
    padding: 1rem 1.5rem;
    border-radius: 30px;
    cursor: pointer;
    transition: color 0.3s linear;
  }

  .hero-contact__btn:hover {
    color: var(--clr-dark);
  }



  .hero__scroll-down {
    color: var(--clr-light);
    width: 2rem;
    height: 2rem;
    display: block;
    margin: 1rem auto 0 auto;
    animation: point-down 4s cubic-bezier(0.73, 0.94, 0.76, 0.91) infinite;
    transform: translateX(-50%);
    position: absolute;
    bottom: 0;
    left: 50%;
  }

  @keyframes point-down {
    0%, 10%, 40%, 100% { transform: translateY(0); }
    25% { transform: translateY(1rem); }
  }

  :global(body.light-mode) .hero-contact__btn::before {
    background: var(--clr-dark);
  }

  :global(body.light-mode) .hero-contact__btn:hover {
    color: var(--clr-light);
  }

  @media (min-width:320px){
    .hero__content-title {
      font-size: 1.7831rem;
    }

 
  }
  
  @media (min-width: 430px) and (max-width: 474px) {
    .hero__content-title {
      font-size: 2.4rem;
    }

    .hero__content-description {
      font-size: .5rem;
    }

    .hero-contact__btn {
      padding: 1.2rem 2rem;
    }

    .hero__scroll-down {
      width: 2.5rem;
      height: 2.5rem;
    }
  }

  /* Medium screens (640px to 767px) */
  @media (min-width: 475px) and (max-width: 550px) {
    .hero__content-title {
      font-size: 2.65rem;
    }

    .hero__content-container {
      gap: 1rem;
    }

    .hero__content-description {
      font-size: .58rem;
    }

    .hero-contact__btn {
      padding: 1.5rem 2.5rem;
    }

    .hero__scroll-down {
      width: 3rem;
      height: 3rem;
    }
  }

  @media (min-width: 551px) and (max-width: 767px){
    .hero__content-title {
      font-size: 3.1rem;
    }

    .hero__content-container {
      gap: 1rem;
    }

    .hero__content-description {
      font-size: .7rem;
    }

    .hero-contact__btn {
      padding: 1.5rem 2.5rem;
    }

    .hero__scroll-down {
      width: 3rem;
      height: 3rem;
    }
  }

  @media (min-width: 768px) and (max-width: 1023px) {
    .hero__content-title {
      font-size: 4.41rem;
      margin-top: 6rem;
    }

    .hero__content-container {
      gap: 2rem;
    }

    .hero__content-description {
      font-size: .9rem;
    }

    .hero-contact__btn {
      padding: 1.8rem 3rem;
    }

    .hero__scroll-down {
      width: 3.5rem;
      height: 3.5rem;
    }
  }


  @media (min-width: 1024px) and (max-width:2559px){
    .hero__content-title {
   
      font-size: 5.93rem;
      text-align: center;
      margin-top: 7rem;
    }

    .hero__content-description {
      font-size: 1rem;
    }

    .hero-contact__btn {
      padding: 2.2rem 4rem;
    }

    .hero__scroll-down {
      width: 4.5rem;
      height: 4.5rem;
    }

    
    :global(body.light-mode) .hero-contact__btn::before {
      background: var(--clr-dark);
    }

    :global(body.light-mode) .hero-contact__btn:hover {
      color: var(--clr-light);
    }
  }


  @media (min-width: 2560px) {

    .hero{
      gap: 5rem;
    }

    .hero__content-container{
      gap: 3rem;
    }

    .hero__content-title {
      font-size: 14.95rem;
    }

    .hero__content-description {
      font-size: 3.2rem;
    }

    .hero-contact__btn {
      padding: 2.5rem 5rem;
    }

    .hero__scroll-down {
      width: 5rem;
      height: 5rem;
    }
  }
</style>
