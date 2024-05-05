<!--Разработать интерфейс корзины товаров, в котором пользователь
может изменять количество товаров в корзине и видеть общую сумму
покупки. Каждый товар представлен в виде блока, содержащего поле
ввода для изменения количества товара и отображение его цены. При
изменении количества товаров в поле ввода, необходимо
автоматически пересчитывать стоимость каждого товара и обновлять
общую сумму покупки.-->

<template>
  <div>
    <div v-for="product in products" :key="product.id">
      <h4>{{ product.nameproduct }}</h4>
      <label for="">Количество товара</label>
      <input type="number" id="count" v-model="product.counter" />
      <h2>Цeна:{{product.price}}</h2>
      <h1>Сумма товара: {{product.counter * product.price}}</h1>
    </div>
    <h1>Сумма:{{totalPrise}}</h1>
  </div>
</template>

<script>
export default {
  name: 'BusketComp',

  data () {
    return {
      products: [
        { id: '1', nameproduct: 'Prod1', counter: 5, price: 10 },
        { id: '2', nameproduct: 'Prod2', counter: 4, price: 20 },
        { id: '3', nameproduct: 'Prod3', counter: 2, price: 15 }
      ]
    }
  },

  mounted () {},

  methods: {

  },
  computed: {
    totalPrise () {
      return this.products.reduce((sum, cur) => sum + cur.price * cur.counter, 0)
    }

  }
}
</script>

<style scoped></style>
