<template>
  <div id="app">
    <img src="./assets/logo.png">
    <h1>{{ msg }}</h1>
    <vue-table
      ref="table"
      :column-name-field="{ prop: ['id', 'name'], name: ['供应商ID', '供应商名称']}"
      :pages="{src: pageSrc, multiple: true}"
      selection
      :row-class-name="['row-1', 'row-2']"
      index
      stripe>
    </vue-table>
  </div>
</template>

<script>
import VueTable from '@/components/Table'
import 'element-ui/lib/theme-chalk/index.css' // element-ui component styles

export default {
  name: 'app',
  components: {VueTable},
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      pageSrc: 'http://daily.qundian.elephtribe.com/api/procurement/wxhc/supplier/query'
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
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
