<template>
  <div v-if="products.length">
    <div class="products-intro">
      <h1>{{ title }}</h1>
      <p>{{ description }}</p>
    </div>

    <div class="filters">
      <div class="search-input">
        <input id="search" type="text" class="field" placeholder="Search..." />
      </div>
    </div>

    <div class="products">
      <template v-for="product in products">
        <product :product="product" :key="product.id" />
      </template>
    </div>
  </div>
</template>

<script>
import '../assets/css/products.css';
import Product from '../components/Product.vue';

export default {
  name: 'Products',
  components: {
    Product,
  },
  data() {
    return {
      title: '',
      description: '',
      products: [],
    };
  },
  created() {
    fetch(
      'https://raw.githubusercontent.com/pttolev/fe-interview/vue/public/data/products.json'
    )
      .then((response) => response.json())
      .then((data) => {
        this.title = data.title;
        this.description = data.description;
        this.products = data.products;
      });
  },
};
</script>
