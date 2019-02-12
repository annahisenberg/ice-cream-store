<template>
    <div>
        <div class="order-box" v-bind:key="order[0]" v-for="order in orders">
            <p class="title">{{order[0]}}</p>
            <p>Chocolate scoops: {{order[1]}}</p>
            <p>Vanilla scoops: {{order[2]}}</p>
            <p>Mint scoops: {{order[3]}}</p>
            <p>Sprinkles: {{order[4]}}</p>
            <p>Chocolae chips: {{order[5]}}</p>
            <p class="title">Total price: {{order[1] + order[2] + order[3] + order[4] + order[5]}}</p>
        </div>
        <input v-if="orders.length > 0" @click="payNow" type="submit" value="Pay Now">
    </div>
</template>

<script>
export default {
    name: 'orders',
    props: ["orders"],
    methods: {
        payNow() {
            alert('Thank you for your order!');
            this.$emit('pay-now');
        }
    }
}
</script>

<style scoped>
    .order-box {
        border: 3px solid darkmagenta;
    }

    .title {
        font-size: 15px;
        font-weight: bold;
        color: green;
    }
</style>
