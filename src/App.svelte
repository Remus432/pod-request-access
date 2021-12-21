<script>
	import Card from "./components/Card.svelte"

	let PodLogo = "assets/logo.svg"
</script>

<main class="app">
	<img class="logo" src={PodLogo} alt="Pod Logo" />
	<Card />
</main>

<style lang="scss">
	@import "./styles/variables.scss";

	.app {
		align-items: center;
		background-blend-mode: overlay;
		background-color: $color-bg;
		background-image: url("/assets/image-host-mobile.jpg");
		background-size: cover;
		background-repeat: no-repeat;
		display: flex;
		flex-direction: column;
		height: 100vh;
		justify-content: center;
		padding: 6.2rem 2.4rem 9.2rem 2.4rem;
		width: 100vw;

		.logo {
			margin-bottom: 5.7rem;
		}
	}
</style>