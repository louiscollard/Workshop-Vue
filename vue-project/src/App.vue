<script>
import ProductDisplay from "./components/ProductDisplay.vue";

export default {
	components: {
		ProductDisplay,
	},
	data() {
		return {
			cart: 0,
			premium: true,
		};
	},
	methods: {
		updateCart() {
			this.cart += 1;
		},
		removeCart() {
			this.cart -= 1;
		},
	},
};
</script>

<template>
	<div class="nav-bar"></div>
	<ProductDisplay :cart="cart" :premium="premium" @add-to-cart="updateCart" @remove-to-cart="removeCart" />
</template>
