<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      名前<input v-model="name">
      <sui-button>Click Here</sui-button>
      <button disabled v-on:click="doAdd">モンスターを追加</button>
      <ul>
        <li v-for = "item in list" v-bind:key="item.id">
          ID.{{item.id}} {{item.name}} {{item.hp}}
        </li>
      </ul>
    </p>

  <sui-dropdown
    placeholder="Gender"
    selection
    :options="options"
    :menu-header="menuHeader"
    :search-in-menu="searchInMenu"
    v-model="current"
  />
  </div>
</template>

<script>
export default {
  // name: 'HelloWorld',
  props: {
    msg: String
  },
  data(){
    return{
      name:'キマイラ',
      list: [
        {id:1, name: 'スライム', hp:100 },
        {id:2, name: 'ゴブリン', hp:200 },
        {id:3, name: 'ドラゴン', hp:500 },
      ],

      current: null,
      searchInMenu: {
        iconPosition: 'left',
      },
      options: [{
        text: 'Male',
        value: 1,
      }, {
        text: 'Female',
        value: 2,
      }],
    }
  },
  methods:{
    doAdd: function(){
      var max = this.list.reduce(function(a,b){
        return a>b.id?a:b.id
      },0)
      this.list.push({
        id:max+1,
        name:this.name,
        hp:500
      })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
