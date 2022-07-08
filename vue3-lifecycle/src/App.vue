<template>
  <h1>{{ count }}</h1>
</template>

<script>
export default {
  data(){
    return {
      count: 2
    }
  },
  beforeCreate(){
    // undefined
    console.log('before Create!', this.count );
  },
  created(){
    // 2
    console.log('Created!', this.count);
  },
  beforeMount(){
    // null html과 연결이 되기전 이라서
    console.log('before Mount!');
    console.log(document.querySelector('h1'));
  },
  mounted(){
    // <h1>2</h1> html과 연결된 후
    console.log('Mounted!');
    console.log(document.querySelector('h1'));
  }
}
</script>