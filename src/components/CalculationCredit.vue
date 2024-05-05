<!--Создайте компонент MortgageCalculator с соответствующим шаблоном и скриптом.
2. В шаблоне компонента разместите поля ввода для суммы кредита, процентной
ставки и срока кредита, а также элементы для отображения ежемесячного платежа
и общей суммы выплаты.
3. Используйте директиву v-model для связывания введенных пользователем
значений с соответствующими свойствами в компоненте.
4. Создайте вычисляемое свойство monthlyPayment, которое будет вычислять
ежемесячный платеж на основе введенных значений суммы кредита, процентной
ставки и срока кредита.
5. Создайте вычисляемое свойство totalPayment, которое будет вычислять общую
сумму выплаты по кредиту, учитывая ежемесячный платеж и срок кредита.
6. Отобразите значения monthlyPayment и totalPayment в соответствующих элементах
шаблона.-->
<template>
  <div>
    <div>
        <label for="loanAmount">loanAmount</label>
        <input type="number" id='loanAmount' v-model.number="loanAmount">
        <label for="interestRate">interestRate</label>
        <input type="number" step='0.01' id='interestRate' v-model.number="interestRate">
        <label for="loanTern">loanTern</label>
        <input type="number" id='loanTern' v-model.number="loanTern">
        <p>{{monthlyPayment}}</p>
        <p>{{totalPayment}}</p>
    </div>

  </div>
</template>

<script>
export default {
  name: 'CalculationCredit',

  data () {
    return {
      loanAmount: 10000000,
      interestRate: 12,
      loanTern: 12

    }
  },

  mounted () {

  },

  methods: {

  },
  computed: {
    monthlyPayment: function () {
      const rate = this.interestRate / 120 / 12
      const tern = this.loanTern
      const principal = this.loanAmount
      const namerator = rate * Math.pow(1 + rate, tern)
      const denominator = Math.row(1 + rate, tern) - 1
      const payment = principal * (namerator / denominator)
      return payment.toFixed(2)
    },
    totalPayment: function () {
      const tern = this.loanTern
      const payment = parseFloat(this.monthlyPayment)
      return (tern * payment).toFixed(2)
    }

  }
}
</script>

<style scoped>

</style>
