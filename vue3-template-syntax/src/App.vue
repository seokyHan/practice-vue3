<template>
  <h1 
    v-once
    @click="add">
    {{ msg }}
  </h1>
  
  <h1 v-html="msg"></h1>
  
  <h1 :class="bindMsg">
    {{ bindMsg }}
  </h1>

  <h1
    :[attr]="'active'"
    @[event]="add">
    {{ bindMsg }}
  </h1>
</template>

<script>
export default {
  data(){
    return {
      msg: '<div style="color: red;">Hello!!</div>',
      bindMsg: 'active',
      attr: 'class',
      event: 'click'
    }
  },
  methods:{
    add(){
      this.bindMsg += '!'
    }
  }
}
</script>

<style scoped>
.active{
    color: royalblue;
}
</style>