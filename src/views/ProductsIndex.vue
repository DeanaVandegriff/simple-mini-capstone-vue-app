<script>
import axios from "axios";

export default {
  data: function () {
    return {
      products: [],
    };
  },

  created: function () {
    axios.get("http://localhost:3000/products.json").then((response) => {
      this.products = response.data;
      console.log("all products", this.products);
    });
  },
};
</script>

<template>
  <h1>smcMart Products!</h1>
  <div v-for="product in products" v-bind:key="product.id">
    <h2>Name: {{ product.name }}</h2>
    <img :src="product.image_url" v-bind:alt="product.title" />
    <a v-bind:href="`/products/${product.id}`">More Info!</a>
  </div>
</template>

<style></style>
