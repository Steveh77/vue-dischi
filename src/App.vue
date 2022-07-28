<template>
  <div id="app">
    <MyHeader :geners-list="genersList" @genre-change="setSelectGenre" />
    <MyMain :select-genre="selectGenre" />
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue';
import MyMain from './components/MyMain.vue';


export default {
  name: 'App',
  components: {
    MyHeader,
    MyMain
  },
  data() {
    return {
      selectGenre: "",
      genersList: ['Rock', 'Pop', 'Metal']
    }
  },
  methods: {
    setSelectGenre(genre) {
      this.selectGenre = genre;
    }
  },
}
</script>

<style lang="scss">
@import './assets/scss/style.scss';
</style>
