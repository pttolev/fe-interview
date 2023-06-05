<template>
  <div class="container" id="app">
    <products />
  </div>
</template>

<script>
import './assets/css/app.css';
import Products from './views/Products.vue';

export default {
  name: 'App',
  components: {
    Products,
  },
};
</script>

<script>
export default {
  name: 'App',
  created() {
    fetch(
      'https://raw.githubusercontent.com/pttolev/fe-interview/vue/public/data/products.json'
    )
      .then((response) => response.json())
      .then((data) => {
        return data;
      });
  },
};
</script>
