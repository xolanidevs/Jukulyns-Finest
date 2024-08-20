<script>
  import { onMount } from 'svelte';
  // import emailjs from 'emailjs-com';

  let name = '';
  let surname = '';
  let email = '';
  let contactNumber = '';
  let message = '';
  let sending = false;
  let success = false;
  let error = '';

  async function handleSubmit(event) {
    event.preventDefault();
    sending = true;
    error = '';
    success = false;

    try {
      // await emailjs.sendForm('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', event.target, 'YOUR_USER_ID');
      success = true;
      name = '';
      email = '';
      contactNumber = '';
      message = '';
    } catch (err) {
      error = 'Failed to send message. Please try again later.';
    } finally {
      sending = false;
    }
  }
</script>

<section id="contact" class="contact container fade-in">
  <h1 class="contact__title title">Contact Us</h1>
  <form class="contact__form" on:submit={handleSubmit}>
    <label for="name">Name <span style="color: red;">*</span></label>
    <input type="text" id="name" name="name" bind:value={name} required>
    <label for="email">Email <span style="color: red;">*</span></label>
    <input type="email" id="email" name="email" bind:value={email} required>
    <label for="contactNumber">Contact numbers <span style="color: red;">*</span></label>
    <input type="text" id="contactNumber" name="contactNumber" placeholder="012 324 6789" bind:value={contactNumber} required>
    <label for="message">Message</label>
    <textarea id="message" name="message" rows="4" placeholder="Singakunceda ngani?" bind:value={message}></textarea>
    <button type="submit" disabled={sending}>Submit</button>
    {#if sending}
      <p>Sending...</p>
    {/if}
    {#if success}
      <p>Your message has been sent successfully!</p>
    {/if}
    {#if error}
      <p>{error}</p>
    {/if}
  </form>

  <div class="contact__alternative">
    <p>Or alternatively, you can contact us on social media:</p>
      <a href="https://www.facebook.com/jukulynsfinest" target="_blank">
        <i class="fa-brands fa-facebook"></i>
      </a>
      <a href="https://www.tiktok.com/@jukulynsfinest?lang=en" target="_blank">
        <i class="fa-brands fa-tiktok"></i>
      </a>
      <a href="https://www.instagram.com/jukulynsfinest/" target="_blank">
        <i class="fa-brands fa-instagram"></i>
      </a>
  </div>
</section>
<style>
  .contact{
  margin-bottom: 5rem;
  max-width: 80%;
  overflow: hidden;
}

.title {
  text-align: center;
}

.contact__form {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  background-color: var(--clr-slate200);
  padding: 2rem;
  border-radius: 8px;
  margin-bottom: 1rem;
  color: var(--clr-dark);
}

.contact__form label {
  font-weight: bold;
}

.contact__form input,
.contact__form textarea {
  padding: 0.5rem;
  border: 1px solid #ccc;
  border-radius: 4px;
}

.contact__form button {
  background-color: #052D23;
  color: white;
  border: none;
  padding: 0.75rem;
  border-radius: 8px;
  cursor: pointer;
  width: 150px;
  margin-left: auto;
  margin-right: auto;
}

.contact__form button:hover {
  background-color: #031d16;;
}

.contact__alternative {
  text-align: center;
}

.contact__alternative p {
  margin-bottom: 1rem;
}

.contact__alternative a {
  margin: 0 1rem;
  color: white;
  text-decoration: none;
  font-weight: bold;
}

.contact__alternative a:hover {
  text-decoration: underline;
}

@media (max-width:768px){
  .title{
    font-size: var(--size-4xl);
  }
}

</style>