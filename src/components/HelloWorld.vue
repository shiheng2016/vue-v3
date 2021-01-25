<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  // data不是一个对象而是一个函数 ? 生成新的实例的时候，data就会返回一个新的对象
  // 私有属性 互不干扰
  data() {
    return {
      color: 'red',
      opacity: 0
    }
  },
  mounted () {
    setInterval(_ => {
      this.opacity >= 1 && (this.opacity = 0)
      this.opacity += 0.2
    }, 300)
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style vars="{ color, opacity }" scoped>
h1 {
  color: var(--color);
  margin: 40px 0 0;
  opacity: var(--opacity);
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
