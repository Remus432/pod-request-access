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

  .pod {
    &__headline {
      color: $color-primary;
      font-size: 2.6rem;
      text-align: center;
      text-transform: uppercase;
      line-height: 3.8rem;
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
  }
</style>