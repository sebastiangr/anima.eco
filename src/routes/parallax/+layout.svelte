<script lang="ts">
  import Background from "$lib/assets/ANIMA_bg-02.jpg";
  import ParallaxTop from "$lib/assets/ANIMA_bg-01.png";
  import ParallaxBottom from "$lib/assets/ANIMA_bg-02.png";

  let mouseX: number = 0;
  let mouseY: number = 0;

  function handleMouseMove(event: MouseEvent) {
    mouseX = (event.clientX / window.innerWidth) * 100;
    mouseY = (event.clientY / window.innerHeight) * 100;
  }
</script>

<div class="body-bg flex items-center justify-center min-h-screen" on:mousemove={handleMouseMove} role="document">
  <div 
    class="bg-top absolute top-0 left-0 w-full h-full"
    style={`background-image: url(${ParallaxTop}); background-position: ${mouseX * 0.1}% ${mouseY * 0.1}%`}>
  </div>
  <div 
    class="bg-bottom absolute top-0 left-0 w-full h-full"
    style={`background-image: url(${ParallaxBottom}); background-position: ${mouseX * 0.2}% ${mouseY * 0.2}%; `}>
  </div>
  <slot />
</div>

<style>
  .body-bg {
    /* background-image: url(${Background}); */
    background: #892b21;
  }
</style>

