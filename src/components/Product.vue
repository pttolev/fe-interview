<template>
  <div class="product">
    <a :href="product.url" class="product-image">
      <img :src="product.image" alt="" />
      <span v-if="product.new || product.sale" class="product-badges">
        <span v-if="product.new" class="product-badge">
          <span class="badge-new">New arrivals</span>
        </span>
        <span v-if="product.sale" class="product-badge">
          <span class="badge-sale">Sale</span>
        </span>
      </span>
    </a>

    <div class="product-content">
      <h2 class="h3">
        <a :href="product.url">{{ product.name }}</a>
      </h2>
      <p>{{ product.description }}</p>
      <div class="product-price">
        <strong>${{ product.price.current }}</strong>
        <span
          v-if="Number(product.price.current) < Number(product.price.regular)"
          >${{ product.price.regular }}</span
        >
      </div>
    </div>
  </div>
</template>

<script>
import '../assets/css/product.css';

export default {
  name: 'Product',
  props: {
    product: Object,
  },
};
</script>
