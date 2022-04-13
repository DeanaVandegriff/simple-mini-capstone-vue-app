<script>
import axios from "axios";

export default {
  data: function () {
    return {
      product: {},
    };
  },
  created: function () {
    axios.get("http://localhost:3000/product/" + this.$route.params.id + ".json").then((response) => {
      console.log(response.data);
      this.product = response.data;
    });
  },
};
</script>

<template>
  <h1>Product</h1>
  <p>{{ product }}</p>
  <a href="/products">Back to all Products</a>
</template>

<style></style>
