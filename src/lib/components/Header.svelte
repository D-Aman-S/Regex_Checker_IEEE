<script>
	import thbLogo from '$lib/assets/icon.png'
	import ham from '$lib/assets/ham.png'
</script>

<header>
	<nav class="border-gray-200 bg-black px-6 py-5">
		<div class="mx-auto flex max-w-screen-xl items-center justify-between ">
			<img
				src={thbLogo}
				class="mr-3 h-12 sm:h-16"
				alt="THBrandenburg"
				draggable="false"
			/>
			<p class="heading">Regex Master</p>
			<div class="text-highlight flex items-center text-center text-xs">
				 <a class="active" href="#home">Home</a>
        <a href="#news">About</a>
        <a href="#contact">Contact</a>
        <a href="#search">Terms Of Use</a>
        <a href="#about">Payment</a>
			</div>
			<img
				src={ham}
				class="mr-3 h-12 sm:h-16"
				alt="THBrandenburg"
				draggable="false"
			/>
		</div>
	</nav>
</header>

<style lang="postcss">
	a{
		margin: auto;
		padding-left: 5px;
		padding-right: 5px;
		font-size: 15px;
	}
	.heading{
		font-size: 60px
	}
	nav {

		@apply border-third border-b-[1.333px];
	}
</style>
