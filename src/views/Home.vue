<template>
  <div class="home">
    <IceCreamStore v-on:add-chocolate-scoop="addChocolateScoop" />
    <ShoppingCart />
  </div>
</template>

<script>
// @ is an alias to /src
import IceCreamStore from '../components/IceCreamStore';
import ShoppingCart from '../components/ShoppingCart';

export default {
  name: 'home',
  components: {
    IceCreamStore,
    ShoppingCart
  },
  data() {
    return {
      chocolate: 0
    }
  },
  methods: {
    addChocolateScoop() {
      this.chocolate = this.chocolate + 1;
      console.log(this.chocolate);
    }
  }
}
</script>
