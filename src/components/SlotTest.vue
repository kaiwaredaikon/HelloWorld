<template>
  <div class="slot-test">
    ここにスロットを埋め込む<slot></slot>

<div class="ui mini form">

  <div class="inline fields">
    <div class="four wide field">
      <!-- <div class="fields"> -->
        <div class="six wide field"> 
          Name
        </div>  
       <div class="ten wide field">
        <input type="text" placeholder="First Name" kl_vkbd_parsed="true">
       </div>
      <!-- </div> -->
    </div>
    
    <div class="four wide field">
      <label>Name</label>
      <input type="text" placeholder="First Name" kl_vkbd_parsed="true">
    </div>
  </div>

  <div class="inline fields">
    <div class="four wide field">
      <!-- <div class="fields"> -->
        <div class="five wide field"> 
          <label>First name</label>
        </div>  
       <div class="eleven wide field">
        <input type="text" placeholder="First Name" kl_vkbd_parsed="true">
       </div>
      <!-- </div> -->
    </div>
    
    <div class="four wide field">
      <label>Name</label>
      <input type="text" placeholder="First Name" kl_vkbd_parsed="true">
    </div>
  </div>

</div>


  </div>
</template>

<script>
export default {
  // name: 'HelloWorld',
  props: {
    value: {
      // type: Object,
      // required: true,
    },
  },
  data(){
    return{
      text: '',
      choice: [],
    }
  },
  updated: function() {
    this.$emit('input', {
      choice: this.choice,
      text: this.text,
    })
  },
  mounted: function() {
    this.choice = this.value.choice
    this.text   = this.value.text
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
