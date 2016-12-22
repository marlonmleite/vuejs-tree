<template>
  <li class="tree-item">
    <div v-on:click="toggleItem">
      {{ item.label }}
      <span v-if="isFolder">{{ isOpen ? '-' : '+' }}</span>
    </div>
    <ul v-if="isFolder" v-show="isOpen">
      <tree-item v-for="child in item.children" v-bind:item="child"></tree-item>
    </ul>
  </li>
</template>

<script>
  export default {
    name: 'tree-item',
    props: {
      item: Object,
      required: true
    },
    data: function () {
      return {
        isOpen: false
      }
    },
    computed: {
      isFolder: function () {
        return this.item.children && this.item.children.length > 0
      }
    },
    methods: {
      toggleItem: function () {
        if (this.isFolder) {
          this.isOpen = !this.isOpen
        }
      }
    }
  }
</script>

<style>
  .tree-item {
    padding: 5px;
  }

  .tree-item div:hover {
    cursor: pointer;
  }
</style>