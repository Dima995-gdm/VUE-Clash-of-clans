<template>
	<div class="wrapper-person">
		<div v-if="item">
			<img :src="item.img" :alt="item.descr" />
			<h1 style="color: #fff" class="title">{{ item.title }}</h1>
			<p>{{ item.descr }}</p>
			<CardFooter :info="item.info"/>
			<div>
				<router-link to="/" class="btn btnPrimary"
					>Back to home</router-link
				>
			</div>
		</div>
	</div>
</template>

<script>
import items from '@/seeders/items.js'
import CardFooter from '@/components/UI/CardFooter'

export default {
	components: {CardFooter},
	data() {
		return {
			item: null
		}
	},
	created() {
		const alias = this.$route.params.itemAlias
		const item = items.find(el => el.alias === alias)

		if (!item) {
			this.$router.push({ name: '404' })
		}
		else {
			this.item = item
		}
		
	}
}
</script>

<style lang="scss">
.wrapper-person {
	text-align: center;
    .card-stats {
        border-radius: 14px;
        margin: 20px 0;
    }
}
</style>
