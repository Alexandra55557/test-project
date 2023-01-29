<template>
	<div class="container">
		<Navbar />
		<Banner />
		<Portfolio />
		<Company />
		<Application />
		<FooterBlock />
	</div>
</template>

<script>
import Navbar from '@/components/Navbar.vue';
import FooterBlock from '@/components/FooterBlock.vue';
import Banner from '@/components/Banner.vue';
import Portfolio from '@/components/Portfolio.vue';
import Company from '@/components/Company.vue';
import Application from '@/components/Application.vue';

export default {
	components: {
		Banner,
		Navbar,
		FooterBlock,
		Portfolio,
		Company,
		Application,
	},
}
</script>

<style lang="scss">
	html {
		margin: 0;
		padding: 0;
		overflow-x: hidden;
		scroll-behavior: smooth;
	}

	body {
		margin: 0;
		padding: 0;
		overflow-x: hidden;
	}

	.container {
		position: relative;
	}
</style>