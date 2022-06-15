<script context="module">
  /** @type {import('@sveltejs/kit').Load} */
  export function load({ error, status }) {
    return {
      props: {
        title: `${status}`
      }
    };
  }
</script>

<script>
  import Sun from '$components/icons/sun.svelte';

  export let title;
</script>

<section class="error-page">
  <header class="wrapper">
    <h1>{title}</h1>
    <p>We couldn't find what you're looking for.</p>
    <div class="sun">
      <Sun />
    </div>
  </header>
</section>

<style lang="scss">
  .error-page {
    @include center;

    height: 100vh;
  }
  header {
    @include center;

    position: relative;
    isolation: isolate;
    overflow: hidden;

    height: rem(300);

    border-radius: 50%;

    h1 {
      position: relative;
      z-index: 2;

      font-size: size(h1);
      font-family: $heading-family;

      color: $primary-500;
      mix-blend-mode: hard-light;
    }
  }
  .sun {
    position: absolute;
    inset: 50% auto;
    z-index: -1;
    width: rem(300);
    height: rem(300);
    color: $primary-50;
  }
</style>
