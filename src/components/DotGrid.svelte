<script>
  let rows = 32
</script>

<div class="dot-grid">
  {#each Array(rows) as _, row}
    <div class={`dot dot-${row+1}`}></div>
  {/each}
</div>

<style lang="scss">
  @import "../styles/variables";
  @import "../styles/animations";
  @import "../styles/mixins";

  .dot-grid {
    bottom: -5vh;
    display: none;
    grid-template-columns: repeat(8, 1fr);
    gap: 2.4rem;
    position: absolute;
    right: 0;
    z-index: 2;

    .dot {
      animation: scaleIn .2s backwards ease-in;
      background-color: $color-primary;
      border-radius: 50%;
      height: .8rem;
      width: .8rem;

      @for $i from 1 through 32 {
        &:nth-of-type(#{$i}) {
          animation-delay: #{$i/8}s;
        }
      }
    }

    @include respond(desktop) {
      display: grid;
    }
  }
</style>