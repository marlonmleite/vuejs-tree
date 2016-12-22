<template>
  <div id="app">
    <tree v-bind:provider="treeProvider"></tree>
  </div>
</template>

<script>
  import Tree from './components/tree/Tree'

  const treeProvider = [
    {
      label: 'Financeiro',
      children: [
        { label: 'Contas a pagar' },
        { label: 'Contas a receber' },
        { label: 'Sem classificação', children: [{ label: 'Energia' }] }
      ]
    },
    { label: 'Infra' },
    { label: 'Desenvolvimento', children: [{ label: 'Java' }, { label: 'Javascript' }] }
  ]

  export default {
    name: 'app',
    data() {
      return {
        treeProvider: treeProvider
      }
    },
    components: {
      Tree
    }
  }
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>