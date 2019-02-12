<template>
  <div class="home">
    <IceCreamStore v-on:add-scoop="addScoop" v-on:add-topping="addTopping" />
    <ShoppingCart v-if="atLeastOneScoop" :chocolate="chocolate" :vanilla="vanilla" :mint="mint" :sprinkles="sprinkles" :chips="chips" v-on:remove-scoop="removeScoop" v-on:remove-topping="removeTopping" v-on:pay-now="payNow" v-on:another-order="anotherOrder" />
    <Orders v-bind:orders="orders" v-on:pay-now="payNow" />
  </div>
</template>

<script>
// @ is an alias to /src
import IceCreamStore from '../components/IceCreamStore';
import ShoppingCart from '../components/ShoppingCart';
import Orders from '../components/Orders';

export default {
  name: 'home',
  components: {
    IceCreamStore,
    ShoppingCart,
    Orders
  },
  data() {
    return {
      chocolate: 0,
      vanilla: 0,
      mint: 0,
      sprinkles: 0,
      chips: 0,
      orders: [],
      orderNumber: 1
    }
  },
  methods: {
    addScoop(flavor) {
      if (flavor === 'chocolate') {
        this.chocolate += 1;
      } else if (flavor === 'vanilla') {
        this.vanilla += 1;
      } else if (flavor === 'mint') {
        this.mint += 1;
      }
    },
    addTopping(topping) {
      if (topping === 'sprinkles') {
        this.sprinkles += 0.25;
      } else if (topping === 'chips') {
        this.chips += 0.25;
      }
    },
    removeScoop(flavor) {
      if (flavor === 'chocolate') {
        this.chocolate -= 1;
      } else if (flavor === 'vanilla') {
        this.vanilla -= 1;
      } else if (flavor === 'mint') {
        this.mint -= 1;
      }
    },
    removeTopping(topping) {
      if (topping === 'sprinkles') {
        this.sprinkles -= 0.25;
      } else if (topping === 'chips') {
        this.chips -= 0.25;
      }
    },
    payNow() {
      this.chocolate = 0;
      this.vanilla = 0;
      this.mint = 0;
      this.sprinkles = 0;
      this.chips = 0;
      this.orders = [];
      this.orderNumber = 1;
    },
    reset() {
      this.chocolate = 0;
      this.vanilla = 0;
      this.mint = 0;
      this.sprinkles = 0;
      this.chips = 0;
    },
    anotherOrder() {
      this.orders.push([`order ${this.orderNumber}`, this.chocolate, this.vanilla, this.mint, this.sprinkles, this.chips]);
      this.orderNumber++;
      this.reset();
    }
  },
  computed: {
    atLeastOneScoop: function() {
      if (this.chocolate > 0 || this.vanilla > 0 || this.mint > 0) {
        return true;
      }
    }
  }
}
</script>
