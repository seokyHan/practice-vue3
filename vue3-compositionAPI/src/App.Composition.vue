<template>
  <h1 @click="increase">
    {{ count }} / {{ doubleCount }}
  </h1>
  <h1>
    {{ message }} / {{ reversedMessage }}
  </h1>
</template>

<script>
// composition에서는 mounted앞에 on을 붙여야함
import {ref, computed, watch, onMounted} from 'vue'

export default{
  // data() {
  //   return {
  //     count: 0,
  //     message: 'Hello World!'
  //   }
  // },
  // computed: {
  //   doubleCount() {
  //     return this.count * 2
  //   },
  //   reversedMessage() {
  //     return this.message.split('').reverse().join('')
  //   }
  // },
  // watch: {
  //     message(newValue) {
  //       console.log(newValue)
  //     }
  // },
  // created(){
  //   console.log(this.message)
  // },
  // mounted() {
  //   console.log(this.count)
  // },
  // methods: {
  //   increase() {
  //     this.count += 1
  //   },
  //   changeMessage(){
  //     this.message = 'Good?!'
  //   }
  // }

  // composition API를 통해 아래로 변경
  // composition api는 아래처럼 props와 attribute에 접근해야함
  // setup (props, context) {
  //   console.log(this.props) -> console.log(props.key)
  //   console.log(this.$attrs) -> console.log(context.attrs)
  // }

  setup() {
    const count = ref(0);
    const doubleCount = computed(() => {
      return count.value * 2
    });
    function increase(){
      count.value += 1;
    }

    const message = ref('Hello World');
    const reversedMessage = computed(() => {
      return message.value.split('').reverse().join('');
    })

    watch(message, newValue => {
      console.log(newValue);
    })

    function changeMessage() {
      message.value = 'Good?!'
    }

    onMounted(() => {
      console.log(count.value);
    })
    

    return {
      message,
      changeMessage,
      reversedMessage,
      count,
      doubleCount,
      increase
    }
  }
}
 
</script>
