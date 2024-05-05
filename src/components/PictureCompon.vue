<template>
  <div>
    <div><img class="big" :src="currentImgUrl" alt=""></div>
      <div>
          <img  class='mini' v-for="(dog, index) in pictures" :key="index" :src="dog" alt="img" @click='imgSelectIndex(index)'/>
      </div>
    </div>
</template>

<script>
export default {
  name: 'PictureCompon',
  data () {
    return {
      currentImgIndex: 0,
      pictures: [
        'https://i6.imageban.ru/out/2023/03/07/abc63f962f6bf74ecade7aeee2880af7.jpg',
        'https://i6.imageban.ru/out/2023/03/07/22816421855b6a880598d705cfb99e96.jpg',
        'https://i7.imageban.ru/out/2023/03/07/1e9a247da8397a6f5908785da606b71a.jpg'
      ]
    }
  },
  computed: {
    currentImgUrl () {
      return this.pictures[this.currentImgIndex]
    }
  },

  mounted () {},
  methods: {
    imgSelectIndex (i) {
      this.currentImgIndex = i
    }
  }
}
</script>

<style scoped>
.mini {
  width: 150px;
}
.big{
  width: 300px;
}
</style>
