<script>
  import LoadingScreen from '$components/loading-screen.svelte';
  import Navigation from '$components/main-navigation.svelte';
  import { loading } from '../store/job-state';
  import '../styles/main.scss';
</script>

{#if $loading}
  <LoadingScreen />
{/if}
<Navigation />
<slot />
