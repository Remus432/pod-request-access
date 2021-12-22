<script>
	import Card from "./components/Card.svelte"
	import DotGrid from "./components/DotGrid.svelte"

	let PodLogo = "assets/logo.svg"
</script>

<main class="app">
	<img class="logo" src={PodLogo} alt="Pod Logo" />
	<Card />
	<DotGrid />
</main>

<style lang="scss">
	@import "./styles/variables";
	@import "./styles/mixins";
	@import "./styles/animations";

	.app {
		align-items: center;
		background-blend-mode: overlay;
		background-color: $color-bg;
		background-image: url("/assets/image-host-mobile.jpg");
		background-size: cover;
		background-origin: center center;
		background-repeat: no-repeat;
		display: flex;
		flex-direction: column;
		height: 100vh;
		justify-content: center;
		padding: 6.2rem 2.4rem 9.2rem 2.4rem;

		.logo {
			margin-bottom: 5.7rem;
			z-index: 2;
		}

		@include respond(tab) {
			align-items: flex-start;
			background-blend-mode: screen;
			background-image: url("/assets/image-host-tablet.jpg");
			background-size: 60% 100%;
			background-position: right;
			height: auto;
			padding-bottom: 25rem;
			position: relative;

			&::before {
				bottom: 0;
				content: url("/assets/bg-pattern-dots.svg");
				position: absolute;
				z-index: 2;
			}

			.logo {
				margin-bottom: 15rem;
			}
		}

		@include respond(desktop) {
			animation: bgZoomIn 1.4s forwards ease-in-out;
			justify-content: flex-start;
			background-image: url("/assets/image-host-desktop.jpg");
			padding: 0;

			&::before {
				display: none;
			}

			.logo {
				animation: fadeInUp 1.4s forwards ease;
			}

			&::after {
				animation: slideReveal 1s forwards ease-in-out;
				background-color: $color-bg;
				content: "";
				height: 100%;
				position: absolute;
				top: 0;
				right: 0;
				width: 100%;
			}

			&::before {
				bottom: -5vh;
				right: 0;
			}
		}
	}


</style>