<template>
  <div id="app">
       <ProductDetails/>
        <NewComponent text='12'/>
        <PictureCompon/>
        <AutoficationComp/>
        <BusketComp/>
     </div>
</template>

<script>
import ProductDetails from './components/ProductDetails.vue'
import NewComponent from './components/NewComponent.vue'
import PictureCompon from './components/PictureCompon.vue'
import AutoficationComp from './components/AutoficationComp.vue'
import BusketComp from './components/BusketComp.vue'

export default {
  name: 'App',
  components: {
    ProductDetails,
    NewComponent,
    PictureCompon,
    AutoficationComp,
    BusketComp
    // CreditComponent,
    // CalculationCredit
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
