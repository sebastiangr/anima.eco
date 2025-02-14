<script lang="ts">    
    import { language } from '../stores/languageStore'; // Importing the language store

    // IMPORT ASSETS
    import Logo from "$lib/assets/ANIMA_logo-white.svg";
    import IconInstagram from "$lib/assets/icon-instagram.svg";
    import IconWhatsapp from "$lib/assets/icon-whatsapp.svg";
    import CatalogES from "$lib/pdf/ANIMA_2025_ES.pdf";
    import CatalogEN from "$lib/pdf/ANIMA_2025_EN.pdf";
</script>

<div class="flex flex-col items-center justify-center min-h-screen">
  <img src={Logo} alt="ANIMA" class="logo mx-auto mt-8 mb-8 hover:scale-110 transition duration-700" />

  <div class="quote mx-auto mt-8 pl-10 pr-10 text-center">
    {#if $language === 'en'}
      <p>
        "...her soul expanded with her eyeballs, and she prayed that she might share<br>
        the majesty of the hills, know the serenity of the plains, <br>
        ...Then, looking down, the red hyacinth, the purple iris <br>
        wrought her to cry out in ecstasy at the goodness, the beauty of nature; ..."
      </p>    
    {:else}
      <p>
        " ... su alma se agrandó con sus ojos e imploró el don de compartir <br>
        la majestad de las colinas, conocer la serenidad de las llanuras, <br>
        ... Luego a sus pies, el jacinto rojo, el iris púrpura, <br>
        le hacían prorrumpir en un grito de éxtasis ante la bondad, la hermosura de la naturaleza; ..."
      </p>
    {/if}
    <span class="mt-5">Virginia Woolf</span>
  </div>

  <h2 class="mt-10 pr-4 pl-4">{ $language === 'en' ? 'Website under construction' : 'Sitio web en construcción' }</h2> <!-- Updated content based on language -->

  <p class="text-center mt-2 pr-4 pl-4">
    { $language === 'en' ? 'We are working on our new website. In the meantime, you can download our catalog.' : 'Estamos trabajando en nuestro nuevo sitio web. Mientras tanto, puedes descargar nuestro catálogo.' }
  </p>

  <a href={$language === 'en' ? CatalogEN : CatalogES} target="_blank" download class="btn-download mt-8 text-white focus:outline-none hover:scale-95 transition duration-300">
    { $language === 'en' ? 'Download catalog' : 'Descargar catálogo' }
  </a>

  <div class="bottom-nav mt-12 mb-8 md:fixed md:bottom-0 md:left-0 md:right-0 md:p-4">
    <ul class="social-icons flex flex-col sm:flex-row justify-center items-center sm:items-baseline gap-4 sm:gap-0">
      <li class="sm:mr-4 ">
        <a href="https://www.instagram.com/anima.eco/" target="_blank" class="flex flex-row items-center transition duration-500 ease-in-out hover:scale-105"> 
          <img class="icon" src={IconInstagram} alt="Instagram" />
          <span>@anima.eco</span>
        </a>
      </li>
      <li>
        <a href="https://wa.me/573146846166" target="_blank" class="flex flex-row items-center transition duration-500 ease-in-out hover:scale-105">
          <img class="icon" src={IconWhatsapp} alt="Whatsapp" />
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
  p {
    color: #eae0d6;
  }
  .logo {
    width: 300px;
  }
  .quote p {
    color: #eae0d6;
    font-family: "Libre Baskerville", serif;
    font-size: 18px;
  }
  .quote  span {
    color: #eae0d6;
    display: block;
    font-family: "Libre Baskerville", serif;
    font-size: 16px;
    font-style: italic;
  }
  .btn-download {
    background-color: #eae0d6;
    border: 2px solid #6b201b;
    border-radius: 20px;
    color: #892b21;
    font-family: "billcorporatenarrow-book", sans-serif;
    font-size: 24px;
    height: 60px;
    line-height: 60px;
    padding-left: 20px;
    padding-right: 20px;
  }
  .icon {
    height: 40px;
    width: 40px;
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

  @media (max-width: 768px) {
    h2 {
      font-size: 24px;
    }
    .logo {
      width: 250px;
    }
    .quote p {
      font-size: 16px;
    }
    .quote span {
      font-size: 14px;
    }
    .btn-download {
      font-size: 20px;
      height: 50px;
      line-height: 50px;
    }
    .icon {
      height: 30px;
      width: 30px;
    }
    ul.social-icons li a span {      
      font-size: 16px;
    }
  }
</style>
