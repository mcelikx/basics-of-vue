<template>
  <div class="product">
    <strong> {{ product.title }}</strong>
    <p>{{ product.description }}</p>
    <strong> Fiyat: {{ product.price }} / Adet: {{ product.count }} </strong>
    <br />
    <button @click="$emit('addToCart', product)">Sepete Ekle</button>
    <button @click="addToCart(product)">Sepete Ekle</button>
  </div>
</template>

<script>
export default {
  props: ["product"],
  methods: {
    addToCart() {
      this.$emit("addToCart", this.product);
    },
  },
};
</script>

<style scoped>
.product {
  border: 2px dashed #000;
  padding: 10px;
  width: 200px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  margin: 10px;
}

.product:hover {
  border: 2px solid green;
  transition: all 1s ease;
}
</style>
