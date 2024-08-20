<footer class="footer">
  <div class="footer__container">
    <div class="footer__description">
      <h2>About Us</h2>
      <p>We are a dedicated team offering professional multimedia services to transform your vision into reality. Connect with us to learn more about our packages and services.</p>
    </div>
    <div class="footer__links">
      <h2>Quick Links</h2>
      <ul>
        <li><a href="#hero">Home</a></li>
        <li><a href="#services">Services</a></li>
        <li><a href="#contact">Contact Us</a></li>
        <li><a href="#about">About Us</a></li>
      </ul>
    </div>
    <div class="footer__contact">
      <h2>Contact Us</h2>
      <p>Email: <a href="mailto:bizwithxolani@gmail.com">jukulynsfinest@gmail.com</a></p>
      <p>Phone: +27 81 710 9252</p>
      <div class="footer__social">
        <a href="#" target="_blank"><i class="fab fa-whatsapp"></i></a>
        <a href="https://www.facebook.com/jukulynsfinest" target="_blank"><i class="fa-brands fa-facebook"></i></a>
        <a href="https://www.youtube.com/@jukulynsfinest2238" target="_blank"><i class="fa-brands fa-youtube"></i></a>
        <a href="https://www.tiktok.com/@jukulynsfinest?lang=en" target="_blank"><i class="fa-brands fa-tiktok"></i></a>
        <a href="https://www.instagram.com/jukulynsfinest/" target="_blank"><i class="fa-brands fa-instagram"></i></a>
      </div>
    </div>
  </div>
  <div class="footer__bottom">
    <p>&copy;2024 Jukulyn’s Finest. All rights reserved.</p>
  </div>
</footer>

<style>
  footer {
    border-top: 1px dotted var(--clr-light);
    padding: 2rem 0;
    color: #a7a7a7;
    overflow: hidden;
  }

  .footer__container {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    padding: 0 1rem;
  }

  .footer__description,
  .footer__links,
  .footer__contact {
    margin: 1rem 0;
    width: 100%;
  }

  .footer__description h2,
  .footer__links h2,
  .footer__contact h2 {
    font-size: 1.5rem;
    margin-bottom: 1rem;
  }

  .footer__links ul {
    list-style: none;
    padding: 0;
  }

  .footer__links li {
    margin: 0.5rem 0;
  }

  .footer__links a {
    color: var(--clr-slate200);
    text-decoration: none;
  }

  .footer__links a:hover {
    text-decoration: underline;
  }

  .footer__social {
    margin-top: 1rem;
  }

  .footer__social a {
    display: inline-block;
    margin-right: 1rem;
    text-decoration: none;
  }

  .footer__social a:hover {
    text-decoration: underline;
  }

  .footer__bottom {
    text-align: center;
    padding: 1rem 0;
    background-color: var(--clr-slate300);
    color: #fff;
    margin-top: 2rem;
  }

  @media (min-width: 768px) {
    .footer__container {
      flex-direction: row;
      justify-content: space-between;
      text-align: left;
      max-width: 1200px;
      margin: 0 auto;
    }

    .footer__description,
    .footer__links,
    .footer__contact {
      width: auto;
      margin: 0 1rem;
    }

    .footer__social {
      margin-top: 0;
    }
  }
  @media (min-width: 1028px){
    .footer {
  border-top: 1px dotted var(--clr-light) ;
  padding: 2rem 0;
  color: #a7a7a7;
}

.footer__container {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

.footer__description,
.footer__links,
.footer__contact {
  flex: 1;
  margin: 0 1rem;
}

.footer__description h2,
.footer__links h2,
.footer__contact h2 {
  font-size: 1.5rem;
  margin-bottom: 1rem;
}

.footer__description p,
.footer__contact p,
.footer__contact a {
  margin: 0.5rem 0;
}

.footer__links ul {
  list-style: none;
  padding: 0;
}

.footer__links li {
  margin: 0.5rem 0;
}

.footer__links a {
  color: var(--clr-slate200);
  text-decoration: none;
}

.footer__links a:hover {
  text-decoration: underline;
}

.footer__social a {
  display: inline-block;
  margin-right: 1rem;
  text-decoration: none;
}

.footer__social a:hover {
  text-decoration: underline;
}

.footer__bottom {
  text-align: center;
  padding: 1rem 0;
  background-color: var(--clr-slate300);
  color: #fff;
}

.footer__bottom p {
  margin: 0;
}

.home{
  position: absolute;
  right :20px;

}
  }
</style>
