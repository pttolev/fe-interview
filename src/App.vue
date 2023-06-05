<template>
  <div id="app">My Vue.js application</div>
</template>

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
