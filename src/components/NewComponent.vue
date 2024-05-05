<template>
  <div>
    <h1>{{text}}</h1>
  </div>
</template>

<script>
export default {
  name: 'NewComponent',
  props: {
    text: String,
    counter: {
      type: Number,
      required: true,
      default () {
        return 10
      }
    }
  }
}
</script>
