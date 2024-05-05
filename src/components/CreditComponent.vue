
<template>
  <div>
    <div v-for="book in books" :key="book.id">
      <h4>{{ book.bookName }}</h4>
      <button @click="toogleDescription(book.id)">Show</button>
      <p v-if="showDescription.includes(book.id)">{{ book.decscription }}{{ book.publicationYare }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CreditComponent',

  data () {
    return {
      books: [
        { id: '1', bookName: 'Dook 1', decscription: 'Description111', publicationYare: '1977' },
        { id: '2', bookName: 'Book 2', decscription: 'Description2222', publicationYare: '2007' },
        { id: '3', bookName: 'Dffffook 1', decscription: 'Description22222', publicationYare: '2015' }
      ],
      showDescription: []
    }
  },

  mounted () {},

  methods: {
    toogleDescription (id) {
      const findIndex = this.showDescription.indexOf(id)
      if (findIndex === -1) {
        this.showDescription.push(id)
      } else {
        this.showDescription.splice(findIndex, 1)
      }
    }
  }
}
</script>

<style scoped></style>
