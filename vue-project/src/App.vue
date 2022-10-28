<script>
export default {
	data() {
		return {
			product: "Socks",
			description: "description",
			image: "./src/assets/images/socks_green.jpeg",
			url: "https://github.com/louiscollard/Workshop-Vue/tree/main/vue-project",
			inStock: true,
			onSale: true,
			details: ["50% coton", "30% wool", "20% polyester"],
			variants: [
				{
					id: 1,
					color: "green",
					image: "./src/assets/images/socks_green.jpeg",
				},
				{
					id: 2,
					color: "blue",
					image: "./src/assets/images/socks_blue.jpeg",
				},
			],
			sizes: ["XS", "S", "M", "L", "XL"],
			cart: 0,
		};
	},
	methods: {
		addToCart() {
			this.cart += 1;
		},
		removeToCart() {
			this.cart -= 1;
		},
		updateImage(variantImage) {
			this.image = variantImage;
		},
	},
};
</script>

<template>
	<div class="nav-bar"></div>

	<div class="product-display">
		<div class="product-container">
			<div class="product-image">
				<a :href="url" target="_blank">
					<img :src="image" />
				</a>
			</div>
			<div class="product-info">
				<h1>{{ product }}</h1>
				<p>{{ description }}</p>
				<p v-if="inStock">In stock</p>
				<p v-else>Out of stock</p>
				<p v-show="onSale">On Sale!</p>
				<div class="list">
					<ul>
						<li v-for="detail in details">
							{{ detail }}
						</li>
					</ul>
					<ul>
						<li v-for="size in sizes">
							{{ size }}
						</li>
					</ul>
				</div>
				<div class="circle__container">
					<div v-for="variant in variants" :key="variant.id" @mouseover="updateImage(variant.image)">
						{{ variant.color }}
					</div>
				</div>
				<div class="button__container">
					<button class="button" @click="addToCart">Add to cart</button>
					<button class="button" @click="removeToCart">Remove to cart</button>
				</div>
			</div>
			<div class="cart">Cart ({{ cart }})</div>
		</div>
	</div>
</template>
