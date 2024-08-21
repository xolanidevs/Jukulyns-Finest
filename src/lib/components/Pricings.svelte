<script>

  import { loadStripe } from '@stripe/stripe-js';

   // Initialize Stripe with  public key
   const stripePromise = loadStripe('pk_test_51PqGjB02EN0NWbe5HFvEIfWfkhN6veElCbfnKTs4rflYr6p8Hy0deNyVYuZbKnVN66kqJWW5S5iMZDNrINqDO9sb00TdUfkn4e');


    // @ts-ignore
    async function handleCheckout(priceId) {
    const stripe = await stripePromise;

    // @ts-ignore
    const { error } = await stripe.redirectToCheckout({
      lineItems: [{ price: priceId, quantity: 1 }],
      mode: 'payment',
      successUrl: `${window.location.origin}/success`, 
      cancelUrl: `${window.location.origin}/canceled`  
    });

    if (error) {
      console.error('Stripe Checkout error:', error);
      // Handle error in redirect
    }
  }

</script>

<section id="pricings" class="pricings container fade-in">
  <h1 class="pricings__title title">Pricings</h1>
  <div class="pricing__container">
    <h4 class="pricings__subtitle">
      For clients looking to book us for only 1 service for the day i.e (Photography or Videography), we charge an hourly rate of R1400 per photoshoot/videoshoot an event.
    </h4>
    <div class="pricings__content-container">
      <article class="pricings__content">
        <h2 class="pricings__content-title">Bronze Package</h2>
        <p class="package-discription">This package is ideal for events</p>
        <span class="pricings__content-description">
          <ul>
            <li>Photography</li>
            <li>Videography</li>
            <li class="notAvailable">Editing</li>
            <li class="notAvailable">Content Creation</li>
            <li class="notAvailable">Directing</li>
          </ul>
        </span>
        <p class="pricings__content-price">R3000</p>
        <!-- Button that triggers Stripe Checkout -->
        <button class="pricings__btn" on:click={() => handleCheckout('price_1PqHAj02EN0NWbe5LRcokiNK')}>Select Package</button>
      </article>

      <article class="pricings__content">
        <h2 class="pricings__content-title">Silver Package</h2>
        <button class="pricings__btn1">Popular</button>
        <p class="package-discription">This ideal is suitable for mid-sized projects</p>
        <span class="pricings__content-description">
          <ul>
            <li>Photography</li>
            <li>Videography</li>
            <li>Editing</li>
            <li class="notAvailable">Content Creation</li>
            <li class="notAvailable">Directing</li>
          </ul>
        </span>
        <p class="pricings__content-price">R5500</p>
        <!-- Button that triggers Stripe Checkout -->
        <button class="pricings__btn" on:click={() => handleCheckout('price_1PqHhU02EN0NWbe5idQqyfeG')}>Select Package</button>
      </article>

      <article class="pricings__content">
        <h2 class="pricings__content-titleGold">Gold Package</h2>
        <p class="package-discription">Ideal for businesses and big projects</p>
        <span class="pricings__content-description">
          <ul>
            <li>Photography</li>
            <li>Videography</li>
            <li>Editing</li>
            <li>Content Creation</li>
            <li>Directing</li>
          </ul>
        </span>
        <p class="pricings__content-price">R10000</p>
        <!-- Button that triggers Stripe Checkout -->
        <button class="pricings__btn" on:click={() => handleCheckout('price_1PqHki02EN0NWbe5ko5kcHjo')}>Select Package</button>
      </article>
    </div>
    <!-- <button class="pricings__btn2">Book A Call</button> -->
  </div>
</section>


<style>

section {
  overflow: hidden;
}

.pricings__title {
  text-align: center;
  margin-bottom: 2rem; 
  font-size: var(--size-4xl);
}

.pricings__subtitle {
  margin-bottom: 1.5rem; 
  max-width: 90%; 
  text-align: center;
  margin-left: auto;
  margin-right: auto;
}

.pricing__container {
  background-color: var(--clr-slate200);
  padding: 20px;
  border-radius: 15px; 
  color: #052D23;
}

.pricings__content-container {
  font-family: 'Clash Display', sans-serif;
  display: block; 
  gap: 1rem;
}

.pricings__content {
  background-color: #f9f9f9;
  padding: 15px; 
  border-radius: 15px; 
  border: 1px solid #052D23;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1); 
  margin-bottom: 1rem; 
}

.pricings__content ul {
  padding-left: 10px; 
}

.pricings__content ul li {
  list-style-type: disc;
}

.pricings__content-title {
  font-size: 1.25rem;
  margin-bottom: 0.5rem; 
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
  font-size: 1rem; 
  margin-bottom: 1rem; 
}

.pricings__btn {
  background-color: #052D23;
  color: #fff;
  border: none;
  padding: 8px 16px;
  border-radius: 15px; 
  cursor: pointer;
  transition: background-color 0.3s ease;
  display: block;
  margin: 0.5rem auto; 
}

.pricings__btn:hover {
  background-color: #021410;
}

.pricings__btn1 {
  display: none;
  position: static;
  background-color: #ffc107;
  color: #fff;
  border: none;
  padding: 5px 10px;
  border-radius: 15px; 
}

/* .pricings__btn2 {
  margin-top: 1rem; 
  text-decoration: underline;
  font-size: 1rem; 
  display: block;
  margin: 1rem auto; 
  background: none;
  border: none;
  cursor: pointer;
} */

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
    display: flex; 
    flex-wrap: wrap; 
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

  /* .pricings__btn2 {
    margin-top: 2rem;
    font-size: var(--size-base);
  } */
}

/* Desktop screens */
@media (min-width: 1024px) {
  .pricings__title{
    font-size: var(--size-10xl);
  }
}

</style>