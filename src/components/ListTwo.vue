<template>
  <div id="list-one">
    <h3 class="title"> product 2 </h3>
    <ul>
      <li v-for="product in saleProducts">
        <span class="name"> {{ product.name }} </span>
        <span class="price"> {{ product.price }} </span>
      </li>
    </ul>
    <button @click="reducePrice">Reduce Price</button>
  </div>
</template>

<script>

  import {mapActions} from 'vuex'
  import {mapGetters} from 'vuex'

  export default {

    computed: {

      products () {
        return this.$store.state.products
      },

      // saleProducts () {
      //   return this.$store.getters.saleProducts
      // }

      ...mapGetters([
          'saleProducts'
        ])
    },

    methods: {

      // reducePrice (amount) {
      //   this.$store.dispatch('reducePrice', amount)
      // }

      ...mapActions([
        'reducePrice'
        ])
    }

  }
</script>

<style scoped>
  #list-one {
    /*text-align: center;*/
    background: #D1E4FF;
    box-shadow: 1px 2px 3px rgba(0,0,0,0,2);
    margin-bottom: 30px;
    padding: 10px 20px;
  }
  #list-one ul {
    padding: 0;
  }
  #list-one li{
    display: inline-block;
    margin-right: 10px;
    margin-top: 10px;
    padding: 20px;
    background: rgba(255,255,255,0.7);
  }
  .title {
    font-weight: 800;
    margin-bottom: 30px;
  }
  .price {
    font-weight: bold;
    color: #860CE8;
  }
</style>