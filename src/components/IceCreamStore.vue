<template>
  <div class="hello">
    <h1>Ice Cream Store</h1>
    <p>Flavors:</p>
    <ul>
      <li>Chocolate - $1 per scoop <button @click="addScoop('chocolate')">Add one scoop to cart</button></li>
      <li>Vanilla - $1 per scoop <button @click="addScoop('vanilla')">Add one scoop to cart</button></li>
      <li>Mint Chocolate Chip - $1 per scoop <button @click="addScoop('mint')">Add one scoop to cart</button></li>
    </ul>

    <p>Toppings:</p>
    <ul>
      <li>Sprinkles - $0.25 <button @click="addTopping('sprinkles')">Add to cart</button></li>
      <li>Chocolate Chips - $0.25 <button @click="addTopping('chips')">Add to cart</button></li>
    </ul>
  </div>
</template>

<script>

export default {
  name: 'IceCreamStore',
  methods: {
    addScoop(flavor) {
      this.$emit('add-scoop', flavor);  
    },
    addTopping(topping) {
      this.$emit('add-topping', topping)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
