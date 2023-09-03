<template>
  <div class="container">
    <div class="products">
      <Product
        @addToCart="cartItems.push($event)"
        :product="product"
        v-for="product in products"
        :key="product.id"
      />
    </div>
    <div class="cart">
      <h1>Sepet</h1>
      <p v-if="cartItems.length === 0">Sepetinizde Ürün Yok :(</p>
      <ul v-for="cartItem in cartItems" :key="cartItem.id">
        <li>{{ cartItem.title }} - {{ cartItem.price }}</li>
      </ul>
    </div>
  </div>
</template>

<script>
import Product from "@/components/Product.vue";
export default {
  components: {
    Product,
  },
  data() {
    return {
      products: [
        {
          id: 1,
          title: "Macbook Pro",
          price: "400 USD",
          count: 5,
          description: "sdfsadfsd",
        },
        {
          id: 2,
          title: "Macbook Air",
          price: "300 USD",
          count: 12,
          description: "AAAAA",
        },
        {
          id: 3,
          title: "Dell XPS",
          price: "200 USD",
          count: 7,
          description: "BBBBB",
        },
      ],
      cartItems: [],
    };
  },
  methods: {},
};
</script>

<style>
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.cart {
  border: 2px dashed #000;
  padding: 10px;
  width: 200px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  margin: 10px;
  background-color: #eee;
}
.products {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: center;
}
</style>
