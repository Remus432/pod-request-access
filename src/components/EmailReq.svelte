<script>
  let isFocused = false
  let errMsg = ""
  let emailRegex = /^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/

  const validateEmail = e => {
    const email = e.target.elements.email.value
    
    if (email == "") {
      errMsg = "Oops! Please add your email!"
    } else if (!emailRegex.test(email)) {
      errMsg = "Oops! Please check your email!"
    } else {
      errMsg = ""
      e.target.elements.email.value = ""
    }

  }
</script>

<form on:submit|preventDefault={validateEmail} class={`req-access ${isFocused ? "focused" : ""}`}>
  <input on:focus={() => isFocused = true} on:blur={() => isFocused = false} class="req-access__email" type="text" name="email" placeholder="Email address" />
  <button class="req-access__btn" type="submit">Request Access</button>
  {#if errMsg}
    <span class="req-access__err-msg">{errMsg}</span>
  {/if}
</form>

<style lang="scss">
  @import "../styles/variables";
  @import "../styles/mixins";
  @import "../styles/animations";

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
      cursor: pointer;
      font-weight: 700;
      padding: 1.4rem 3.2rem;
    }

    @include respond(tab) {
      align-items: center;
      background-color: $color-input;
      border-radius: 2.8rem;
      flex-direction: row;
      padding: .5rem;
      position: relative;

      &.focused {
        outline: 1px solid $color-primary;
      }

      &__err-msg {
        bottom: -3rem;
        color: $color-alert;
        font-size: 1.2rem;
        font-weight: 700;
        left: 2rem;
        position: absolute;
      }

      &__email {
        margin-bottom: 0;

        &:focus {
          outline: none;
        }
      }
    }

    @include respond(desktop) {
      animation: fadeInUp 1s backwards .5s ease;

      &__btn:hover {
        background-color: lighten($color-primary, 20%);
      }
    }
  }
</style>