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
				},
				{
					id: 2,
					color: "blue",
				},
			],
			sizes: ["XS", "S", "M", "L", "XL"],
		};
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
					<div v-for="variant in variants" :key="variant.id">
						{{ variant.color }}
					</div>
				</div>
			</div>
		</div>
	</div>
</template>
