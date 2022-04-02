<template>
	<div class="wrapper">
		<Header />
		<div class="wrapper-content">
			<div class="container">
				<router-view />
			</div>
		</div>

		<Footer />
	</div>
</template>

<script>
import Header from '@/components/Header-main'
import Footer from '@/components/Footer-main'
export default {
	components: { Header, Footer }
}
</script>

<style></style>
