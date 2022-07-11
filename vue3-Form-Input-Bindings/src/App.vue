<template>
  <h1>{{ msg }}</h1>
  <input
    type="text"
    v-model="msg" />

  <h1>{{ checked }}</h1>
  <input
    type="checkbox"
    v-model="checked" />

  <!-- v-model은 한글 입력시 한박자 늦게 입력됨 
  한글 입력시는 단방향방식으로 해야함
  <h1>{{ msg }}</h1>
  <input
    type="text"
    :value="msg"
    @input="msg = $event.target.value" /> -->

  <!-- 다 입력되고 엔터나 탭키나 focus가 해제될때 change -->
  <h1>{{ text }}</h1>
  <input
    type="text"
    v-model.lazy="text" />
</template>

<script>
export default{
  data() {
    return {
      text: "hi",
      msg: 'hello world',
      checked: false
    }
  },
  watch: {
    text(){
      console.log(this.text);
    }
  }
}
</script>