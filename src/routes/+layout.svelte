<script lang="ts">
  import '../app.postcss';
  import { dev } from '$app/environment';
  import { injectAnalytics } from '@vercel/analytics/sveltekit';
  import Background from "$lib/assets/ANIMA_bg.jpg";
  import ParallaxTop from "$lib/assets/ANIMA_bg-01.png";
  import ParallaxBottom from "$lib/assets/ANIMA_bg-02.png";
  import { language } from '../stores/languageStore'; // Updated import path

  let mouseX: number = 0;
  let mouseY: number = 0;
  let isMobile: boolean;
  let handleMouseMove: (event: MouseEvent) => void;

  if (typeof window !== 'undefined') {
    isMobile = window.innerWidth <= 992;

    handleMouseMove = (event: MouseEvent) => {
      if (!isMobile) {
        mouseX = (event.clientX / window.innerWidth) * 100;
        mouseY = (event.clientY / window.innerHeight) * 100;
      }
    };

    window.addEventListener('resize', () => {
      isMobile = window.innerWidth <= 992;
    });
  }

  injectAnalytics({ mode: dev ? 'development' : 'production' });

  export function toggleLanguage() {
    language.update((current: string) => (current === 'en' ? 'es' : 'en')); // Explicitly typed parameter
  }
</script>

<button 
    on:click={toggleLanguage} 
    class="language-toggle absolute top-4 right-4 bg-white text-black p-2 rounded shadow-md hover:bg-gray-200 transition duration-300">
    {#if $language === 'en'}
        ES
    {:else}
        EN
    {/if}
</button>

<div class="body-bg flex items-center justify-center min-h-screen" on:mousemove={handleMouseMove} role="document" style={`${isMobile ? `background-image: url(${Background});` : ''}`}>
  {#if !isMobile}
    <div 
      class="bg-top absolute top-0 left-0 w-full h-full pointer-events-none"
      style={`background-image: url(${ParallaxTop}); background-position: ${mouseX * 0.1 + '% ' + mouseY * 0.1 + '%'}`}>
    </div>
    <div 
      class="bg-bottom absolute top-0 left-0 w-full h-full pointer-events-none"
      style={`background-image: url(${ParallaxBottom}); background-position: ${mouseX * 0.2 + '% ' + mouseY * 0.2 + '%'}`}>
    </div>
  {/if}

  <slot />
</div>

<style>
  button.language-toggle {
    background-color: transparent;
    border: none; 
    box-shadow: none;
    color: #eae0d6;
    font-family: "Libre Baskerville", serif;
    font-style: italic;
    font-size: 1.5rem;        
  }
  .body-bg {
    background: #892b21;
    background-size: 105%;
    background-position: center center;
  }
  .bg-top, .bg-bottom {
    background-size: 102%;
    background-position: center center;
  }
</style>

