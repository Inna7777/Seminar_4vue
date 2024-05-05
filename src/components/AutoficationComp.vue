<!--Создайте компонент "Аутентификация" (Authentication),
// который будет отображать форму входа или сообщение об
// успешной аутентификации в зависимости от переданного
// пропса isAuthenticated. Используйте директиву v-if для
// условного отображения разных элементов в шаблоне
// компонента.-->

<template>
  <div>
    <form  v-if='!isAutofication' action="#">
      <label for="login">Login</label>
      <input type="text" id="login" v-model="userLogin" />
      <label for="password">Pass</label>
      <input type="password" id="password" v-model="userPassword" />
      <button @click='formheck' >Enter</button>
    </form>
    <h3 v-else>Авторизация успешна!</h3>
  </div>
</template>

<script>
export default {
  name: 'AutoficationComp',
  data () {
    return {
      isAutofication: false,
      userLogin: '',
      userPassword: ''
    }
  },
  methods: {
    formheck () {
      if (this.userLogin && this.userPassword) {
        this.isAutofication = true
      }
    }
  }
}
</script>

<style scoped></style>
