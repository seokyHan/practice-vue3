<template>
  <li>{{ name }}?!</li>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      default: ''
    }
  }
}
</script>

// scoped 속성은 다른 component에 영향을 안줌 여기에만 적용
<style scoped lang="scss">
h1{
    color: red !important;
}
</style>