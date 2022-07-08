<template>
  <!-- 해당 component에 slot으로 전달 -->
  <MyBtn>Banana</MyBtn>
  <MyBtn :color="color">Apple</MyBtn>
  <MyBtn large color="royalblue" >Cherry</MyBtn>
  <MyBtn >strawberry</MyBtn>
</template>

<script>
import MyBtn from '~/components/MyBtn'

export default {
  components: {
    MyBtn
  },
  data() {
    return {
      color: '#000'
    }
  }
}
</script>