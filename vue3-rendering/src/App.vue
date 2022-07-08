<template>
  <button @click="add">
    Add
  </button>
  <h1>{{ msg }}</h1>
  <h1>{{ reversedMessage }}</h1>
</template>

<script>


export default{
  data() {
    return {
      msg: 'Hello?'
    }
  },
  computed: {
    // computed에 있는건 캐싱처리가 되어 내부에서 로직을 처리 해놓은걸 불러오기만 함(읽기전용 Getter)
    // reversedMessage() {
    //   return this.msg.split('').reverse().join('')
    // }
    reversedMessage: {
      get() {
        return this.msg.split('').reverse().join('')
      },
      set(value){
        this.msg = value;
      }
    }
  },
  // msg와 reversedMessage는 감시하고 있음. 변경이 감지되면 console에 찍히도록 구현
  // 첫번째 매개변수로 변경될 값을 사용 가능
  watch:{
    msg(value) {
      console.log('msg:', value);
    },
    reversedMessage() {
      console.log('reversedMessage', this.reversedMessage);
    }
  },
  methods: {
    add() {
      this.msg = 'Good!'
    }
  }
}
</script>