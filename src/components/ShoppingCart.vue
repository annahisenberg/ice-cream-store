<template>
    <div>
        <h3>Cart:</h3>
        <p>Flavors:</p>
        <ul>
            <li v-if="chocolate">Chocolate: {{chocolate}} <button @click="removeScoop('chocolate')">Remove One</button></li>
            <li v-if="vanilla">Vanilla: {{vanilla}} <button @click="removeScoop('vanilla')">Remove One</button></li>
            <li v-if="mint">Mint Chocolate Chip: {{mint}} <button @click="removeScoop('mint')" >Remove One</button></li>
        </ul>
        <p>Toppings:</p>
        <ul>
            <li v-if="sprinkles">Sprinkles: {{sprinkles}} <button @click="removeTopping('sprinkles')" >Remove One</button></li>
            <li v-if="chips">Chocolate chips: {{chips}} <button @click="removeTopping('chips')" >Remove One</button></li>
        </ul>
        <h3>Total price: ${{chocolate + vanilla + mint + sprinkles + chips}}</h3>
        <input @click="payNow" type="submit" value="Pay Now">
    </div>
</template>


<script>
export default {
    name: 'ShoppingCart',
    props: ["chocolate", "vanilla", "mint", 'sprinkles', 'chips'],
    methods: {
        removeScoop(flavor) {
            this.$emit('remove-scoop', flavor);
        },
        removeTopping(topping) {
            this.$emit('remove-topping', topping);
        },
        payNow() {
            alert('Thank you for your order!');
            this.$emit('pay-now');
        }
    }
}
</script>


<style>

</style>
