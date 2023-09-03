<template>
  <div class="container">
    <p>{{ msg }}</p>
    <p>{{ reversedMsg }}</p>
    <button @click="msg = reverseMsg()">
      <span>Reverse Message</span>
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      msg: "Welcome to Your Vue.js App",
    };
  },
  computed: {
    // a computed getter
    reversedMsg: function () {
      // `this` points to the vm instance
      return this.msg.split("").reverse().join("");
    },
  },
  methods: {
    reverseMsg: function () {
      return this.msg.split("").reverse().join("");
    },
  },
  watch: {
    msg: function (newVal, oldVal) {
      console.log("new: %s, old: %s", newVal, oldVal);
    },
  },
};
</script>

<style></style>
