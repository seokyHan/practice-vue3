<template>
  <button @click="handler">
    Click me!
  </button>

  <button @click="handlerParam('msg', $event)">
    Click msg
  </button>

  <button @click="handlerA(), handlerB()">
    Click msg
  </button>

  <!-- event.preventDefault를 vue.js방식으로 
  @click.once once는 말그대로 한번만 실행 -->
  <a href="https://naver.com"
     target="_blank"
     @click.prevent="testPrevent">
     Naver
  </a>

  <!-- event bubbling(자식에서 부모로) 방지 stop
  event capturing방지 @event.capture.stop 
  @event.self는 해당 이벤트가 걸려있는 영역만 parent에 걸려있다면 child 영역 클릭시 동작 X 
  passive 로직처리와 event 처리를 분리하기 때문에 속도가 올라감-->
  <div class="parent" @click="evePropagationA">
    <div class="child" @click.stop="evePropagationB">
    </div>
  </div>

<div>
  <input type="text" @keydown.enter="keyHandler" />
</div>
</template>

<script>
export default {
  methods: {
    handler(event){
      console.log(event);
      console.log(event.target.textContent)
    },
    handlerParam(msg, event){
      console.log(msg);
      console.log(event);
    },
    handlerA() {
      console.log('A')
    },
    handlerB() {
      console.log('B')
    },
    testPrevent() {
      console.log("ABC");
    },
    evePropagationA(){
      console.log('prop A')
    },
    evePropagationB(){
      console.log('prop B')
    },
    keyHandler() {
      console.log('Enter!')
    }
  }
}
</script>

<style scoped lang="scss">
  .parent{
    width: 200px;
    height: 100px;
    background-color: royalblue;
    margin: 10px;
    padding: 10px;
    .child{
      width: 100px;
      height: 100px;
      background-color: orange;
    }
  }
</style>