<form class="req-access">
  <input class="req-access__email" type="email" placeholder="Email address" />
  <button class="req-access__btn" type="submit">Request Access</button>
</form>

<style lang="scss">
  @import "../styles/variables.scss";

  .req-access {
    display: flex;
    flex-direction: column;
    margin-top: 4.8rem;

    &__email {
      background-color: $color-input;
      border: none;
      border-radius: 2.8rem;
      caret-color: $color-white;
      color: #fff;
      padding: 1.4rem 3.2rem;
      margin-bottom: 1.6rem;

      &:focus {
        outline: 1px solid $color-primary;
      }

      &::placeholder {
        font-weight: 700;
      }
    }

    &__btn {
      background-color: $color-primary;
      border: none;
      border-radius: 2.8rem;
      color: $color-bg;
      font-weight: 700;
      padding: 1.4rem 3.2rem;
    }
  }
</style>