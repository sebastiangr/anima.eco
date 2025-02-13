<script lang="ts">
  import Logo from "$lib/assets/ANIMA_logo-white.svg";
  import IconInstagram from "$lib/assets/icon-instagram.svg";
  import IconWhatsapp from "$lib/assets/icon-whatsapp.svg";
</script>


<div class="flex flex-col items-center justify-center min-h-screen">
<img src={Logo} alt="Sebastian Gonzalez Logo" class=" logo mx-auto mt-8 mb-8" />
<h2>Sitio web en construcción</h2>

<button class="mt-8 text-white bg-blue-700 hover:bg-blue-900 focus:outline-none focus:ring-4 focus:ring-offset-2 focus:ring-blue-500 py-2 px-4 rounded-md">
  Ver catálogo
</button>

<div class="bottom-nav fixed bottom-0 left-0 right-0 p-4">
  <div class="flex flex-row justify-center items-center">
    <ul>
      <li>
        <a href="https://www.instagram.com/anima.eco/"> <img class="w-10 h-10" src={IconInstagram} alt="Instagram" />@anima.eco</a>
      </li>
      <li>
        <a href="https://wa.me/573146846166"> <img class="w-10 h-10" src={IconWhatsapp} alt="Whatsapp" />+57 314 6486166 / +57 300 3060724</a>
      </li>
    </ul>
  </div>
</div>
</div>



<style>
.logo {
  width: 250px;
}
</style>