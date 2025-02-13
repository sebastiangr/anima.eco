<script lang="ts">
    import Logo from "$lib/assets/ANIMA_logo-white.svg";
    import IconInstagram from "$lib/assets/icon-instagram.svg";
    import IconWhatsapp from "$lib/assets/icon-whatsapp.svg";
    import { language } from '../stores/languageStore'; // Importing the language store
</script>

<div class="flex flex-col items-center justify-center min-h-screen">
  <img src={Logo} alt="ANIMA" class="logo mx-auto mt-8 mb-8 hover:scale-110 transition duration-700" />
  <h2>{ $language === 'en' ? 'Website Under Construction' : 'Sitio web en construcción' }</h2> <!-- Updated content based on language -->

  <a href="https://www.google.com" target="_blank" class="btn-download mt-8 text-white focus:outline-none hover:scale-95 transition duration-300">
    { $language === 'en' ? 'View catalog' : 'Ver catálogo' }
  </a>

  <div class="bottom-nav mt-12 sm:fixed sm:bottom-0 sm:left-0 sm:right-0 sm:p-4">
      <ul class="social-icons flex flex-col sm:flex-row justify-center items-center sm:items-baseline gap-4 sm:gap-0">
        <li class="sm:mr-4 ">
          <a href="https://www.instagram.com/anima.eco/" target="_blank" class="flex flex-row items-center transition duration-500 ease-in-out hover:scale-105"> 
            <img class="w-10 h-10" src={IconInstagram} alt="Instagram" />
            <span>@anima.eco</span>
          </a>
        </li>
        <li>
          <a href="https://wa.me/573146846166" target="_blank" class="flex flex-row items-center transition duration-500 ease-in-out hover:scale-105">
            <img class="w-10 h-10" src={IconWhatsapp} alt="Whatsapp" />
            <span>+57 314 6486166 / +57 300 3060724</span>
          </a>
        </li>
      </ul>
  </div>
</div>

<style>
  h2 {    
    color: #eae0d6;
    font-family: "Libre Baskerville", serif;
    font-size: 32px;
    text-align: center;
  }
  .btn-download {
    background-color: #eae0d6;
    border: 2px solid #6b201b;
    border-radius: 20px;
    color: #892b21;
    font-family: "Libre Baskerville", serif;
    font-style: italic;
    font-size: 24px;
    height: 60px;
    line-height: 60px;
    padding-left: 20px;
    padding-right: 20px;
  }
  .logo {
    width: 300px;
  }
  ul.social-icons li {
    list-style: none;
  }
  ul.social-icons li a {
    will-change: transform;
  }
  ul.social-icons li a:hover {
    filter: blur(0px);
  }
  ul.social-icons li a span {
    color: #eae0d6;    
    font-size: 18px;
    padding-left: 10px;
  }
</style>
