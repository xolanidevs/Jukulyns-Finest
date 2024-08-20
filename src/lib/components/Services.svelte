<script>
  // const services = [
  //   { title: "Pre-Production", id: 1 },
  //   { title: "Production", id: 2 },
  //   { title: "Post-Production", id: 3 },
  //   { title: "Equipment rental", id: 4 }
  // ];

  const serviceDetails = [
  { title: "Photography", icon: "fa-solid fa-camera", items: ["Product Photography", "Event Photography", "Lifestyle Photography"] },
  { title: "Videography", icon: "fa-solid fa-video", items: ["Music Videography", "Event Videography", "Promotional Videos", "Corporate Videos"] },
  { title: "Content Creation", icon: "fa-solid fa-pen-to-square", items: ["Script Writing", "Content Strategy", "Campaign Planning", "Concept Development"] },
  { title: "Directing", icon: "fa-solid fa-bullhorn", items: ["Scene Direction", "Talent Direction", "Onset Direction"] },
  { title: "Editing", icon: "fa-solid fa-film", items: ["Video Editing", "Photo Editing and Retouching", "Colour Grading", "Visual Effects (VFX)"] },
  { title: "Equipment Rental", icon: "fa-solid fa-truck-ramp-box", items: ["360 Photobooth", "Photography & Video Equipment", "Sound Rental"] }
];
</script>

<section id="services" class="services container fade-in">
  <h1 class="services__title title">Services</h1>
  <img class="j" src="j2.svg" alt="">
  <h4 class="services__subtitle">Our comprehensive offerings ensure that your project is handled with the utmost expertise and creativity from start to finish. We pride ourselves on our commitment to quality and our ability to bring your vision to life. Our services are divided into four key areas:</h4>
  
  <div class="service__contentWrap">
    {#each serviceDetails as detail}
      <div class="service__content">
        <h2 class="service__content-title">
          <i class="{detail.icon}"></i>
          {detail.title}
        </h2>
        <ul class="service__content-list">
          {#each detail.items as item}
            <li>{item}</li>
          {/each}
        </ul>
      </div>
    {/each}
    <div class="cta-button">
      <a href="#contact" class="cta-link">Hire Us!</a>
    </div>
  </div>
</section>

<style>
  /* Base styles for mobile-first design */
  .services {
    position: relative;
    padding: 2rem 1rem;
    background: linear-gradient(rgba(11,11,11,.7), rgba(11,11,11,.7));
    color: var(--clr-light);
    overflow: hidden;
  }

  .services__title{
    font-size: var(--size-4xl);
    margin-bottom: 0;
    text-align: center;
  }

  .services__title, .services__subtitle {
    margin: 0 auto;
  }
  
  .services__subtitle {
    color: var(--clr-gray);
    font-size: var(--size-sm);
    margin-bottom: 2rem;
  }

  .service__contentWrap {
    display: flex;
    flex-direction: column;
    gap: 2rem;
    
  }

  .service__content {
    border: 1px solid var(--clr-light);
    padding: 1rem;
    border-radius: 20px;
    display: flex;
    flex-direction: column;
    gap: 1rem;
    box-shadow: 5px 5px 8px rgba(0, 0, 0, 0.5);
    transition: transform 0.5s ease;
  }

  .service__content:hover {
    transform: translateY(-5px);
  }

  i {
    padding-right: 1rem;
  }
  
  .service__content-title {
    font-size: 1.25rem;
  }

  .service__content-list {
    list-style-type: none;
    padding: 0;
    font-size: 0.875rem;
  }

  .service__content-list li {
    margin-bottom: 0.5rem;
    /* padding-left: 1rem; */
  }

  .cta-button {
    text-align: center;
    margin-top: 2rem;
  }

  .cta-link {
    display: inline-block;
    padding: 0.75rem 1.5rem;
    border: 1px dotted var(--clr-light);
    border-radius: 20px;
    text-decoration: none;
    color: var(--clr-light);
    transition: all 0.3s ease;
    animation: shake 3s ease-in-out infinite;
  }

  @keyframes shake {
    0%, 100% { transform: translateX(0); }
    25% { transform: translateX(-5px); }
    50% { transform: translateX(5px); }
    75% { transform: translateX(-5px); }
  }

  /* Enhancements for larger screens */
  @media (min-width: 640px) {
    .services__title {
      font-size: 1.75rem;
    }

    .service__content-title {
      font-size: 1.5rem;
    }

    .service__content-list {
      font-size: 1rem;
    }
  }

  @media (min-width: 768px) {

    .services__title {
      font-size: 2rem;
    }


    .services__subtitle {
      max-width: 60ch;
      font-size: 1.125rem;
    }

    .service__contentWrap {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 3rem;
    }

    .cta-button {
      grid-column: 1 / -1;
    }

    .cta-link {
      font-size: 1rem;
    }
  }

  @media (min-width: 1024px) {

    .services__title{
      font-size: var(--size-10xl);
    }

    .services__subtitle {
      max-width: 90ch;
      text-align: center;
    }

    .services {
      padding: 4rem 2rem;
    }

    .service__contentWrap {
      grid-template-columns: repeat(3, 1fr);
    }

    .service__content {
      padding: 1.5rem;
      border-radius: 30px;
    }
  }

  @media (min-width: 1440px) {
    .services__title {
      font-size: var(--size-5xl);
    }

    .services__subtitle {
      max-width: 70ch;
      font-size: 1.25rem;
    }

    .service__contentWrap {
      grid-template-columns: repeat(4, 1fr);
    }

    .service__content-title {
      font-size: 1.75rem;
    }

    .service__content-list {
      font-size: 1.125rem;
    }

    .cta-link {
      font-size: 1.125rem;
      padding: 1rem 2rem;
    }
  }
</style>
