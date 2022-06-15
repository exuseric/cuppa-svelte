<script>
  import { weather as w } from '../../routes/store/weather';
</script>

<header class="weather__header">
  <div class="wrapper">
    <section class="weather">
      <header>
        <h1>{$w.name}</h1>
        <h2 class="weather__temp">
          {Math.floor($w.main.temp)}
          <span>&deg;</span>
        </h2>
      </header>

      <p class="weather__type">
        <span class="txt">
          {$w.weather[0].main}
        </span>
        <span>
          ({$w.weather[0].description})
        </span>
      </p>
    </section>
  </div>
</header>

<style lang="scss">
  .weather__header {
    // @include center;
    padding-top: calc($nav-height + rem(60));
    width: 100%;
    height: 100vh;
    // background-color: $primary-50;
  }
  .weather {
    display: flex;
    flex-direction: column;
    align-items: center;

    max-width: rem(350);

    padding: $spacing-lg $spacing-md;
    text-align: center;

    background-color: transparentize($color: $primary-50, $amount: 0.85);
    border: 2px solid transparentize($color: $primary-50, $amount: 0.75);
    border-radius: 50% / 15%;
  }

  .weather header {
    line-height: 1.125;

    h1 {
      font-family: $heading-family;
      font-size: size(h4);
      color: $primary-50;
    }
  }
  .weather__temp {
    position: relative;
    isolation: isolate;

    font-size: calc(size(h1) + rem(60));
    font-weight: 100;
    color: $primary-50;

    width: fit-content;

    span {
      position: absolute;
      top: 20%;
      left: 100%;

      transform: translate(-50%, -50%);

      font-size: size(h5);
      font-weight: 600;
    }
  }
  .weather__type {
    display: flex;
    flex-direction: column;
    align-items: center;

    font-weight: 600;
    color: $primary-50;

    .txt {
      font-size: size(h5);
    }
  }

  .change-temp {
    @include grid-flow-col;

    width: rem(100);
    margin-top: rem(40);

    border-radius: rem(40);
    overflow: hidden;

    button {
      font-weight: 600;
      font-size: size(body-sm);

      width: rem(50);
      height: inherit;
      padding: 0;

      color: $neutral-500;
      background-color: $primary-900;
    }

    .active {
      color: $primary-500;
      background: $primary-50;
    }
  }
</style>
