<template>
  <div>
    <h1>Добавить заметку</h1>
    <label>Текст заметки</label><br>
    <textarea cols="30" rows="10" v-model="textt"></textarea><br>
    <label>Тэги </label><br>
    <input type="text" v-model="tag" placeholder="Пишите тэг через пробел"><br>
    <router-link :to="{name:'home'}"><button @click="clc">Сохранить</button></router-link>
  </div>
</template>

<script>
  import all from '../all'
  export default {
    data() {
      return {
        tag: '',
        textt: null,
        dates: '2019-06-12',
        all: [],
      }
    },
    methods: {
      clc() {
        this.all = {
          tag: this.tag.split(' '),
          textt: this.textt,
          dates: this.dates,
        }
        if(this.tag !== '' && this.all.textt !== null){
          all.all.push(this.all)
        }
      }
    },
  }
</script>

<style scoped>
  h1{
    margin-top: 10px;
  }
  label{
    font-weight: bold;
  }
  textarea, input{
    width: 100%;
    margin-bottom: 10px;
  }
</style>