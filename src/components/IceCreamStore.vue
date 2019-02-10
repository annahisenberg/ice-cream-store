<template>
  <div class="hello">
    <h1>Ice Cream Store</h1>
    <p>Flavors:</p>
    <ul>
      <li>Chocolate - $1 per scoop <button @click="addChocolateScoop">Add one scoop to cart</button></li>
      <li>Vanilla - $1 per scoop <button>Add one scoop to cart</button></li>
      <li>Mint Chocolate Chip - $1 per scoop <button>Add one scoop to cart</button></li>
    </ul>

    <p>Toppings:</p>
    <ul>
      <li>Sprinkles - $0.25 <button>Add to cart</button></li>
      <li>Chocolate Chips - $0.25 <button>Add to cart</button></li>
    </ul>
  </div>
</template>

<script>

export default {
  name: 'IceCreamStore',
  methods: {
    addChocolateScoop() {
      this.$emit('add-chocolate-scoop');
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
