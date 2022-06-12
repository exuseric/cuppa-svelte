<header class="nav-bar">
  <div class="wrapper">
    <a href="/" class="logo">
      <img src="/logo/main.webp" alt="logo" class="logo__img" />
      <span class="logo__txt">Cuppa</span>
    </a>

    <nav class="nav">
      <ul class="menu">
        <li>
          <a href="/" aria-disabled="true" class="menu__link">Home</a>
        </li>
        <li>
          <a href="/recipes" class="menu__link">Recipes</a>
        </li>
        <li>
          <a href="/about" class="menu__link">About</a>
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

    width: 100%;
    height: $nav-height;

    background-color: $primary-50;
  }
  .logo {
    @include grid-flow-row;
    justify-content: start;
    // gap: $spacing-sm;

    text-decoration: none;
    width: fit-content;
    height: rem(70);

    border-radius: rem(10);

    &__img {
      height: rem(50);
      aspect-ratio: 1 / 1;

      object-fit: contain;
      object-position: center;
    }

    &__txt {
      font-weight: 600;

      color: $primary-500;
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
    color: $neutral-900;
    text-decoration: none;
  }
</style>
