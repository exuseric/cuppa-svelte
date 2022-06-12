<script>
  import Search from '../components/icons/search.svelte';
  import Close from '../components/icons/close.svelte';
  import Location from './icons/location.svelte';
</script>

<form action="/weather" class="search">
  <div class="form-group copy-container__body">
    <div class="form-group__input">
      <label for="search" class="form__label sr-only"> Just search it! </label>
      <input
        class="form__input"
        type="search"
        name="search"
        id="search"
        placeholder="example: Paris, TX"
        aria-label="example: Paris, TX"
        required
        aria-required="true"
      />
      <div class="form-group__actions">
        <button class="search-btn icon-btn" type="submit" aria-label="search">
          <Search />
        </button>
        <button class="close-btn icon-btn" type="reset" aria-label="reset">
          <Close />
        </button>
      </div>
    </div>
    <div class="form-group__button">
      <button class="location-btn outline-btn" type="button" aria-labelledby="label">
        <span class="txt" id="label"> Use my location </span>
        <span class="icon-btn">
          <Location />
        </span>
      </button>
    </div>
  </div>
</form>

<style lang="scss">
  .form-group {
    position: relative;
    isolation: isolate;

    width: 100%;
    // max-width: rem(750);

    display: inline-flex;
    flex-direction: column;
    gap: $spacing-sm;

    // border-radius: 2% / 5%;
    overflow: hidden;

    &__input {
      width: 100%;
    }
  }
  .form-group__button {
    align-self: center;
    width: fit-content;

    @include screen(medium) {
      align-self: flex-start;
    }
  }

  .form__label {
    color: $neutral-900;
    padding: $spacing-md 0;
  }
  .form__input {
    appearance: none;

    font-weight: 600;
    font-size: size(h6);

    width: 100%;
    padding: $spacing-md $spacing-md;

    color: $neutral-900;

    border: rem(2) solid transparent;

    outline-color: currentColor;

    &::placeholder {
      color: $neutral-900;
    }
  }

  .form__input,
  .form-group__actions {
    background-color: $primary-500;
  }
  .form-group__actions {
    @include grid-flow-col;
    position: absolute;
    top: 27%;
    left: 85%;
    transform: translate(-50%, -50%);

    button {
      transform: scale(0);
      opacity: 0;
      visibility: hidden;
      transition: all 0.5s cubic-bezier(0.68, -0.55, 0.265, 1.55);
    }

    button:not(:first-child) {
      transition-delay: 0.15s;
    }

    @include screen(medium) {
      left: 93%;
    }
  }
  .search-btn {
    color: $primary-500;
    background-color: $neutral-900;

    border: 2px solid transparent;
    border-radius: 50%;
  }

  .close-btn {
    color: $neutral-900;
    background-color: transparent;
  }

  .location-btn {
    display: flex;
    flex-flow: row;
    align-items: center;
    justify-content: space-between;

    color: $neutral-900;
    // background-color: $neutral-500;

    width: 100%;
  }

  form:focus-within {
    .form-group__actions > button {
      opacity: 1;
      visibility: visible;
      transform: scale(1);
    }
  }
</style>
