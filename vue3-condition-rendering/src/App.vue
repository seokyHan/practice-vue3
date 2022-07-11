<template>
  <button @click="handler">
    Click me!
  </button>

  <!-- v-if render -->
  <h1 v-if="isShow">
    Hello?
  </h1>
  <h1 v-else-if="count > 3">
    Count > 3
  </h1>
  <h1 v-else>
    Good
  </h1>
  
  <!-- template을 통해 grouping 할 수 있음 최상위 template에는 v-if 이런거 사용못함 -->
  <template v-if="isShow">
    <h1>Title</h1>
    <p>Paragraph 1</p>
    <p>Paragraph 2</p>
  </template>

  <!-- v-show 개발자 도구로 보면 style에 display: none상태로 되어 있음 -->
  <!-- v-show 는 DOM에 남아있지만 v-if는 실제 조건부 렌더링 -->
  <!-- 자주 전환하면 v-show가 좋고 런타임시 조건변경 없다면 v-if가 더 나음 -->
  <h1 v-show="isShow">
    HiHi
  </h1>
</template>

<script>
export default {
  data(){
    return {
      isShow: false,
      count: 0
    }
  },
  methods: {
    handler(){
      this.isShow = !this.isShow
      this.count += 1
    }
  }
}
</script>