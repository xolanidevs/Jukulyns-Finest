<script>
  import { onMount } from 'svelte';

  let images = [];
  let currentIndex = 0;

  onMount(() => {
    images = Array.from(document.querySelectorAll('#imageWrap img'));
    images[currentIndex].classList.add('active');

    const interval = setInterval(shuffleImages, 5000);
    return () => clearInterval(interval);
  });

  function shuffleImages() {
    images[currentIndex].classList.remove('active');
    currentIndex = (currentIndex + 1) % images.length;
    images[currentIndex].classList.add('active');
  }
</script>

<section id="about" class="about container fade-in">
  <h1 class="about__title title">About us</h1>
  <div class="about__content-container">
    <div class="about__image-wrap" id="imageWrap">
      <img class="active" src="/images/About-image1.jpg" alt="About Us">
      <img src="/images/About-image2.jpg" alt="About Us 2">
      <img src="/images/About-image3.jpg" alt="About Us 3">
    </div>
    <div class="about__content">  
      <p class="about__description">
        <span class="about__description-title">Our Story</span><br><br>
        Established in Soshanguve, 2018, we were driven by our initial passion for content creation in comedy via our Youtube channel <a href="https://www.youtube.com/@jukulynsfinest2238" target="_blank" class="link">Jukulyn's Finest</a>. We later expanded our services to multimedia production - specializing in full event production and media production. Our focus is mainly on events photography, videography, content creation, editing and directing. The name "Jukulyn's Finest" was inspired by the location we came from which is in Jukulyn, Soshanguve. Beyond everything else, we value high-quality production and we appreciate good humour of course!
        <br>
        <!-- <span><a href="/about-full" class="read-more">Read more</a></span> -->
      </p>
    </div>
  </div>
</section>

<style>
  .about__title {
    font-size: var(--size-4xl);
    text-align: center;
  }

  .about__content-container {
    display: flex;
    flex-direction: column-reverse;
    margin-top: 2rem;
    gap: 2rem;
  }

  .about__image-wrap {
    display: flex;
    gap: 10px;
    flex: 1;
    height: auto;
    border-radius: 1rem;
    position: relative;
    margin-bottom: 3rem;
  }

  .about__image-wrap img {
    width: 100%;
    height: 200px;
    border-radius: 1rem;
    object-fit: cover;
    position: absolute;
    top: 0;
    left: 0;
    transition: opacity 1s ease-in-out;
    opacity: 0;
  }

  .about__image-wrap img.active {
    opacity: 1;
  }

  .about__content {
    flex: 1;
    display: flex;
    transition: color 0.3s;
  }

  .about__description {
    font-family: sans-serif;
    font-weight: 300;
    color: var(--clr-gray);
    text-align: left;
    font-size: var(--size-sm);
  }

  .link {
    transition: color 0.3s;
  }

  .link:hover {
    color: rgb(247, 0, 0);
  }

  /* .read-more {
    text-decoration: underline;
    transition: opacity 0.3s;
  }

  .read-more:hover {
    opacity: 0.5;
  } */

  /* Breakpoints for larger screens */
  @media (min-width: 640px) {
    .about__title {
    font-size: var(--size-6xl);
  }

  .about__description {
    font-size: var(--size-sm);
  }

  }

  @media (min-width: 768px) {
    .about__title {
      font-size: var(--size-8xl);
    }

    .about__image-wrap img {
      height: 350px;
    }

    .about__description {
      font-size: var(--size-lg);
    }
  }

  @media (min-width: 1024px) {
      .about__title {
      margin: 5rem auto 0 auto;
      text-align: center;
      font-size: var(--size-10xl);
    }

    .about__content-container {
      display: flex;
      margin-top: 5rem;
      flex-direction: row-reverse;
      justify-content: space-between;
    }

    .about__image-wrap {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      grid-template-rows: repeat(2, 1fr);
      gap: 10px;
      flex: 1;
      height: auto;
      border-radius: 1rem;
      position: relative;
    }

    .about__image-wrap img {
      width: 100%;
      height: 100%;
      border-radius: 1rem;
      object-fit: cover;
      position: absolute;
      top: 0;
      left: 0;
      transition: opacity 1s ease-in-out;
      opacity: 0;
    }

    .about__image-wrap img.active {
      opacity: 1;
    }

    .about__content {
      flex: 1;
      display: flex;
      flex-direction: column;
      justify-content: top;
      align-items: start;
      transition: color .3s;
    }

    .about__description {
      font-family: sans-serif;
      max-width: 50ch;
      vertical-align: top;
      font-weight: 300;
      color: var(--clr-gray);
      font-size: var(--size-base);
    }

  }

  @media (min-width: 1440px) {
    .about__title {
      font-size: var(--size-12xl);
    }

    .about__image-wrap img {
      height: 450px;
    }

    .about__description {
      font-size: var(--size-base);
    }
  }
</style>
