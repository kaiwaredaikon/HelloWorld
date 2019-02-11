<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <hello-world v-show="flg" msg="Welcome to Your Vue.js App2"/>
    <hello-world v-show="flg2" msg="Welcome to Your Vue.js App"/>
    <button v-on:click="changeFlg">flgダゾーン</button>

    <slot-test v-model="data">実はここがスロットコンテンツ</slot-test>
    <!-- {{data}} -->
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import SlotTest from './components/SlotTest.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    SlotTest
  },
  data(){
    return{
      flg: true,
      flg2: false,
      data: {
        choice: ['A', 'B'],
        text: '初期値',
      }
    }
  },
  methods:{
    changeFlg: function(){
       this.flg = !this.flg
       this.flg2 = !this.flg2
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
