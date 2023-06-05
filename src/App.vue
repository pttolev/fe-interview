<template>
  <div id="app">My Vue.js application</div>
</template>

<script>
import './assets/css/normalize.css';

export default {
  name: 'App',
  created() {
    fetch('./../public/data/products.json')
      .then((response) => response.json())
      .then((data) => {
        console.log(data);

        return data;
      });
  },
};
</script>
