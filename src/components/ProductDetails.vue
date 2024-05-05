<template>
  <div>
    <div v-for="(item, index) in product" :key="index">
      <p>{{ item.name }}</p>
      <p>{{ formattedPrice(item.price) }}</p>
      <p>{{ availabilityStatus(item.available) }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProductDetails',

  data () {
    return {
      product: [
        {
          name: 'Milk 1',
          price: 3.99,
          available: true
        },
        {
          name: 'Milk 2',
          price: 9.99,
          available: false
        },
        {
          name: 'Milk 3',
          price: 4.99,
          available: true
        }
      ]
    }
  },

  methods: {
    formattedPrice (price) {
      return '$' + price.toFixed(2)
    },

    availabilityStatus (available) {
      return available ? 'Available' : 'Out of stock'
    }
  }
}
</script>

<style scoped></style>
