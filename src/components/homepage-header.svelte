<script>
  import SearchBar from './search-bar.svelte';
</script>

<header>
  <div class="grid">
    <div class="grid__child">
      <div class="heading copy-container__body">
        <h1>Tea recipes with your weather.</h1>
      </div>
      <SearchBar />
    </div>
  </div>
</header>

<style lang="scss">
  @use 'sass:math';

  header {
    height: fit-content;
    background-color: $primary-50;

    .grid {
      @include content-grid;
      height: 100vh;
      &__child {
        display: flex;
        flex-flow: column;
        gap: $spacing-md;

        place-content: center;
        grid-column: 1 / -1;
      }
    }
  }

  .heading {
    text-align: left;

    h1 {
      font-size: size(h3);
      font-family: $heading-family;
      color: $primary-500;
      line-height: 1.125;

      @include screen(large) {
        font-size: size(h1);
      }
    }
  }
</style>
