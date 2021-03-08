<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: 'nextTick',
  data() {
    return {
      msg: 'world'
    }
  },
  mounted () {
    // 作为一个 Promise 使用 (2.1.0 起新增，详见接下来的提示)
    Vue.nextTick().then(function () {
        // DOM 更新了
      })
    }
}
</script>