<template>
  <ul class="tree">
    <tree-item v-for="treeItem in provider" v-bind:item="treeItem"></tree-item>
  </ul>
</template>

<script>
  import TreeItem from './TreeItem'

  export default {
    props: {
      provider: Array
    },
    components: {
      TreeItem
    }
  }
</script>