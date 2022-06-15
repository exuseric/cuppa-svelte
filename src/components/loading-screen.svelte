<script>
  import { fade } from 'svelte/transition';
  import Compass from './icons/compass.svelte';
</script>

<section class="loading-screen" transition:fade>
  <header class="wrapper info copy-container__body">
    <div class="icon-btn">
      <Compass />
    </div>

    <h1>Tasting the air</h1>
  </header>
</section>

<style lang="scss">
  .loading-screen {
    position: fixed;
    inset: 0 0 auto;
    z-index: 100;

    @include center;

    width: 100%;
    height: 100vh;

    font-family: $heading-family;

    color: $primary-50;
    background-color: $primary-500;
  }

  .info {
    @include center;

    .icon-btn {
      justify-self: center;

      width: rem(60);
      height: rem(60);
    }
  }

  .icon-btn > svg {
    height: inherit;
  }
</style>
