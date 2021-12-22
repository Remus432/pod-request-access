<script>
  import EmailReq from "./EmailReq.svelte"

  let applePodcastIcon = "assets/apple-podcast.svg"
  let googlePodcastIcon = "assets/google-podcasts.svg"
  let pocketCastIcon = "assets/pocket-casts.svg"
  let spotifyIcon = "assets/spotify.svg"
</script>

<section class="pod">
  <h1 class="pod__headline">Publish Your Podcasts <span>Everywhere</span></h1>
  <p class="pod__description">Upload your audio to Pod with a single click. We’ll then distribute your podcast to Spotify, Apple Podcasts, Google Podcasts, Pocket Casts and more!</p>
  <div class="pod__icon-group">
    <img class="pod__icon" src={spotifyIcon} alt="Publish on Spotify" />
    <img class="pod__icon" src={applePodcastIcon} alt="Publish on Apple Podcast" />
    <img class="pod__icon" src={googlePodcastIcon} alt="Publish on Google Podcast" />
    <img class="pod__icon" src={pocketCastIcon} alt="Publish on Pocket Cast" />
  </div>
  <EmailReq />
</section>

<style lang="scss">
  @import "../styles/variables";
  @import "../styles/mixins";
  @import "../styles/animations";

  .pod {
    z-index: 2;

    &__headline {
      color: $color-primary;
      font-size: 2.6rem;
      text-align: center;
      text-transform: uppercase;
      line-height: 3.8rem;

      span {
        color: $color-white;
      }
    }

    &__description {
      color: $color-text;
      font-size: 1.5rem;
      line-height: 2.5rem;
      margin-top: 1.6rem;
      text-align: center;
    }

    &__icon-group {
      align-items: center;
      display: flex;
      justify-content: space-between;
      margin-top: 3.3rem;

      .pod__icon {
        width: 6rem;
      }
    }

    @include respond(tab) {
      align-items: flex-start;
      background-color: $color-bg;
      display: flex;
      flex-direction: column;
      padding-top: 9.3rem;

      &__headline {
        font-size: 4.8rem;
        line-height: 5.6rem;
        position: relative;
        text-align: left;
      }

      &__description {
        text-align: left;
        width: 60%;
      }

      &__icon-group {
        margin-top: 6.4rem;
        order: 2;

        .pod__icon {
          width: 10rem;

          &:not(:last-of-type) {
            margin-right: 4rem;
          }
        }
      }
    }

    @include respond(desktop) {
      max-width: 50%;

      &__headline {
        animation: textZoomIn 1s forwards ease-in-out;

        &::after {
          animation: slideReveal 1.2s forwards ease;
          @include transitionOverlay;
        }
      }

      &__description {
        animation: textZoomIn 1s forwards ease-in-out;
        
        &::after {
          animation: slideReveal 1s forwards .5s ease;
          @include transitionOverlay;
        }
      }

      &__icon {
        &:nth-of-type(1) {
          animation: fadeInUp .8s backwards .4s ease-in-out;
        }
        &:nth-of-type(2) {
          animation: fadeInUp .8s backwards .8s ease-in-out;
        }
        &:nth-of-type(3) {
          animation: fadeInUp .8s backwards 1.2s ease-in-out;
        }
        &:nth-of-type(4) {
          animation: fadeInUp .8s backwards 1.6s ease-in-out;
        }
      }
    }
  }
</style>