<script>
  import Github from './icons/github.svelte';
</script>

<header class="nav-bar">
  <div class="wrapper">
    <a href="/" class="logo">
      <img src="/logo/light.webp" alt="logo" class="logo__img" />
      <span class="logo__txt">Cuppa</span>
    </a>

    <nav class="nav">
      <ul class="menu">
        <li>
          <a href="/" aria-disabled="true" class="menu__link">Home</a>
        </li>
        <li>
          <a href="/recipes" aria-disabled="true" disabled class="menu__link">Recipes</a>
        </li>
        <li>
          <a href="/about" aria-disabled="true" disabled class="menu__link">About</a>
        </li>
      </ul>
    </nav>
  </div>
</header>

<style lang="scss">
  .nav-bar {
    display: inline-grid;

    position: fixed;
    inset: 0 0 auto;

    height: $nav-height;

    background-color: none;
  }
  .logo {
    @include grid-flow-row;
    justify-content: center;
    // gap: $spacing-sm;

    text-decoration: none;
    height: rem(70);
    aspect-ratio: 1 / 1;

    border-radius: rem(10);

    &__img {
      height: rem(40);
      aspect-ratio: 1 / 1;

      object-fit: contain;
      object-position: center;
    }

    &__txt {
      font-weight: 600;

      color: $neutral-50;
    }
  }

  .wrapper {
    width: 100%;
  }

  .nav {
    display: inline-grid;
  }

  .wrapper,
  .menu {
    @include flex-wrap-row;
    align-content: center;
  }

  .wrapper {
    justify-content: space-between;
  }

  .menu {
    gap: $spacing-md;
  }

  .menu,
  .menu li {
    appearance: none;
    list-style: none;
  }

  .menu__link {
    font-weight: 600;
    color: $neutral-50;
    text-decoration: none;
  }
</style>
