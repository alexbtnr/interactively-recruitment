<template>
  <footer id="footer" class="footer">
    <div class="container">
      <div class="footer-container">
        <div class="contact">
          <p>
            <i class="las la-2x la-envelope"></i>
            <span>
              Email:
              <a href="mailto:alex.butnaru1102@gmail.com" class="email">
                alex.butnaru1102@gmail.com
              </a></span
            >
          </p>
          <p>
            <i class="las la-2x la-phone"></i>
            <span> Phone: 0751 704 584 </span>
          </p>
        </div>
        <p class="copyright">
          Copyright &copy; 2021 Alex Butnaru
        </p>
        <div class="socials">
          <a href="https://alex-butnaru-portfolio.netlify.app/" target="_blank">
            <i class="las la-2x la-user-circle"></i>
          </a>
          <a href="https://github.com/alexbtnr" target="_blank">
            <i class="lab la-2x la-github"></i>
          </a>
          <a
            href="https://www.linkedin.com/in/alex-butnaru-21a4861b4/"
            target="_blank"
          >
            <i class="lab la-2x la-linkedin"></i>
          </a>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
  export default {
    name: "Footer",
  };
</script>

<style>
  footer {
    background: #333;
    color: #eee;
    width: 100%;
  }

  .footer-container {
    display: flex;
    justify-content: space-around;
    align-items: center;
    width: 100%;
    height: 5rem;
  }

  .footer-container .contact p {
    display: flex;
    justify-content: flex-start;
    align-items: flex-end;
  }

  .footer-container .contact p span {
    border-bottom: 1px solid transparent;
  }

  .footer-container .contact p a.email,
  .footer-container .socials a {
    color: #eee;
    cursor: pointer;
  }

  .footer-container .contact p a.email:hover {
    border-bottom: 1px solid #abcffd;
    color: #abcffd;
  }

  .footer-container .socials i {
    transition: all 0.5s ease;
    border-radius: 50%;
    margin-left: 1rem;
  }

  .footer-container .socials i:hover {
    transform: scale(1.2);
    color: #abcffd;
  }

  @media (max-width: 768px) {
    footer.footer {
      height: 100%;
      height: 15rem;
    }
    footer.footer .container {
      width: 95%;
      height: 100%;
      display: flex;
      justify-content: center;
      align-items: center;
    }
    .footer-container {
      flex-direction: column;
      justify-content: center;
      align-items: center;
      gap: 2rem;
    }
    .socials {
      display: flex;
      justify-content: space-evenly;
      width: 100%;
    }

    .socials i {
      margin: 0;
    }
  }
  @media (max-width: 825px) {
    footer.footer .container {
      width: 95%;
    }
  }
</style>
