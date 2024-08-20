<script>
  import { goto } from '$app/navigation';

  function selectPackage(packageName) {
s
    alert(`You selected the ${packageName} package!`);

  }

  function bookCall() {

    goto('/Contact');
  }
</script>

<section id="pricings" class="pricings container fade-in">
  <h1 class="pricings__title title">Pricings</h1>
  <div class="pricing__container">
    <h4 class="pricings__subtitle">For clients looking to book us for only 1 service for the day i.e (Photography or Videography), we charge an hourly rate of R1400 per photoshoot/videoshoot an event.</h4>
    <div class="pricings__content-container">
      <article class="pricings__content">
        <h2 class="pricings__content-title">Bronze Package</h2>
        <p class="package-discription">This package is ideal for events</p>
        <ul class="pricings__content-description">
          <li>Photography</li>
          <li>Videography</li>
          <li class="notAvailable">Editing</li>
          <li class="notAvailable">Content Creation</li>
          <li class="notAvailable">Directing</li>
        </ul>
        <p class="pricings__content-price">R3000</p>
        <button class="pricings__btn" on:click={() => selectPackage('Bronze')}>Select Package</button>
      </article>
      <article class="pricings__content">
        <h2 class="pricings__content-title">Silver Package</h2>
        <button class="pricings__btn1">Popular</button>
        <p class="package-discription">This ideal is suitable for mid-sized projects</p>
        <ul class="pricings__content-description">
          <li>Photography</li>
          <li>Videography</li>
          <li>Editing</li>
          <li class="notAvailable">Content Creation</li>
          <li class="notAvailable">Directing</li>
        </ul>
        <p class="pricings__content-price">R5500</p>
        <button class="pricings__btn" on:click={() => selectPackage('Silver')}>Select Package</button>
      </article>
      <article class="pricings__content">
        <h2 class="pricings__content-titleGold">Gold Package</h2>
        <p class="package-discription">Ideal for businesses and big projects</p>
        <ul class="pricings__content-description">
          <li>Photography</li>
          <li>Videography</li>
          <li>Editing</li>
          <li>Content Creation</li>
          <li>Directing</li>
        </ul>
        <p class="pricings__content-price">R10000</p>
        <button class="pricings__btn" on:click={() => selectPackage('Gold')}>Select Package</button>
      </article>
    </div>
    <button class="pricings__btn2" on:click={bookCall}>Book A Call</button>
  </div>
</section>

<style>
  /* Mobile-first styles */
section {
  overflow: hidden;
}

.pricings__title {
  text-align: center;
  margin-bottom: 2rem; /* Adjusted for mobile view */
}

.pricings__subtitle {
  margin-bottom: 1.5rem; /* Adjusted for mobile view */
  max-width: 90%; /* Adjusted for mobile view */
  text-align: center;
  margin-left: auto;
  margin-right: auto;
}

.pricing__container {
  background-color: var(--clr-slate200);
  padding: 20px; /* Adjusted for mobile view */
  border-radius: 15px; /* Adjusted for mobile view */
  color: #052D23;
}

.pricings__content-container {
  font-family: 'Clash Display', sans-serif;
  display: block; /* Stack items on mobile */
  gap: 1rem;
}

.pricings__content {
  background-color: #f9f9f9;
  padding: 15px; /* Adjusted for mobile view */
  border-radius: 15px; /* Adjusted for mobile view */
  border: 1px solid #052D23;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1); /* Adjusted for mobile view */
  margin-bottom: 1rem; /* Adjusted for mobile view */
}

.pricings__content ul {
  padding-left: 10px; /* Adjusted for mobile view */
}

.pricings__content ul li {
  list-style-type: disc;
}

.pricings__content-title {
  font-size: 1.25rem; /* Adjusted for mobile view */
  margin-bottom: 0.5rem; /* Adjusted for mobile view */
}

.pricings__content-description {
  margin-bottom: 1rem;
}

.notAvailable{
  color: #27272a;
  text-decoration: line-through;
}

.pricings__content-price {
  font-weight: bold;
  font-size: 1rem; /* Adjusted for mobile view */
  margin-bottom: 1rem; /* Adjusted for mobile view */
  margin-top: 1rem; /* Adjusted for mobile view */
}

.pricings__btn {
  background-color: #052D23;
  color: #fff;
  border: none;
  padding: 8px 16px; /* Adjusted for mobile view */
  border-radius: 15px; /* Adjusted for mobile view */
  cursor: pointer;
  transition: background-color 0.3s ease;
  display: block;
  margin: 0.5rem auto; /* Adjusted for mobile view */
}

.pricings__btn:hover {
  background-color: #021410;
}

.pricings__btn1 {
  display: none;
  position: static; /* Move button inside content block for mobile */
  background-color: #ffc107;
  color: #fff;
  border: none;
  padding: 5px 10px;
  border-radius: 15px; /* Adjusted for mobile view */
}

.pricings__btn2 {
  margin-top: 1rem; /* Adjusted for mobile view */
  text-decoration: underline;
  font-size: 1rem; /* Adjusted for mobile view */
  display: block;
  margin: 1rem auto; /* Adjusted for mobile view */
  background: none;
  border: none;
  cursor: pointer;
}

.notAvailable {
  text-decoration: line-through;
  opacity: 0.5;
}

/* Tablet and larger screens */
@media (min-width: 768px) {
  .pricings__title {
    margin-bottom: 3rem;
  }

  .pricings__subtitle {
    margin-bottom: 2rem;
    max-width: 70%;
  }

  .pricing__container {
    padding: 30px;
    border-radius: 30px;
  }

  .pricings__content-container {
    display: flex; /* Flex layout for larger screens */
    flex-wrap: wrap; /* Allow wrapping */
    gap: 1rem;
  }

  .pricings__content {
    flex: 1;
    margin-bottom: 20px;
  }

  .pricings__content-title {
    font-size: 1.5rem;
    margin-bottom: 10px;
  }

  .pricings__content-price {
    font-size: 1.25rem;
    margin-bottom: 1.5rem;
    margin-top: 1.5rem;
  }

  .pricings__btn {
    padding: 10px 20px;
    border-radius: 30px;
  }

  .pricings__btn1 {
    position: absolute;
    top: 5%;
    right: 5%;
  }

  .pricings__btn2 {
    margin-top: 2rem;
    font-size: var(--size-base);
  }
}

/* Desktop screens */
@media (min-width: 1024px) {

}

</style>