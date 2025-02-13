<script lang="ts">
  import '../app.postcss';
  import { dev } from '$app/environment';
  import { injectAnalytics } from '@vercel/analytics/sveltekit';
 
  injectAnalytics({ mode: dev ? 'development' : 'production' });
</script>

<div class="body-bg flex items-center justify-center min-h-screen">
  <slot />
</div>