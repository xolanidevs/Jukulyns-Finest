<script>
  export let data;
</script>

<section class="container">
  <h1>Payment Successful!</h1>
  <p>Thank you for your purchase. Your transaction was successful.</p>
  <p>You will receive an email confirmation shortly.</p>
  <a href="/">Go back to homepage</a>
</section>

<style>
  section {
    display: flex;
    flex-direction: column;
    gap: 2rem;
    text-align: center;
    margin-top: 10rem;
    margin-bottom: 10rem;
    background: var(--clr-slate200);
    padding: 2rem 2rem;
    /* width: auto; */
    color: #333;
    border-radius: 30px;
  }
  a {
    display: block;
    margin: 0 auto;
    padding: 10px 20px;
    background-color: #4caf50;
    color: white;
    text-decoration: none;
    border-radius: 5px;
  }

  @media (min-width: 768px){
    section {
    
    padding: 2rem 3rem;
    width: fit-content;

  }
  }
</style>
