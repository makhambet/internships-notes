<template>
  <div class="home">
    <router-link to="/about">
      <button class="add">
        Добавить
      </button>
    </router-link>
    <h1>Мои заметки</h1>
    
    <ol>
      <li class="flex" v-for="(a, i) in all" :key="i">
        <p>{{a.textt}}</p>
        <p>
          <span v-for="item in a.tag" :key="item.id">
            {{ item }}
          </span>
        </p>
        <button class="dltBtn" @click="removeBtn(i)">Delete</button>
        {{a.dates}}
      </li>
    </ol>
  </div>
</template>

<script>
// @ is an alias to /src

import all from '../all'
export default {
  name: 'home',
  data() {
    return {
      all: [
        { title :  '' },
        { textt : '' },
      ],
    }
  },
  mounted () {
    this.all = all.all
  },
  methods: {
    name() {
      this.all = all.all
    },
    removeBtn(id){
      return all.all.splice(id, 1)
    }
  },
  components: {
    // notes,
  }
  
}
</script>

<style scope>
  .add{
    float: right;
    top: 0;
    color: #fff;
    background: #2792E6;
    width: 100px;
    height: 30px;
    margin-top: 10px;
    border: none;
    cursor: pointer;
    font-size: 20px;
  }
  span{
    background: #2792E6;
    padding: 3px 10px;
    margin: 0 5px 5px 0;
  }
  .dltBtn{
    background: #2792E6;
    border: none;
    padding: 3px 7px;
    color: #fff;
    cursor: pointer;
    float: right;
    font-size: 20px;
  }
</style>

