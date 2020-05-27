<template>
  <div>
    <h1>Header Component</h1>
    <button v-on:click="changeTitleHeader">Change title from CompHeader.vue</button>
    <h3>{{ title }}</h3>
  </div>
</template>

<script>
export default {
  name: "header-component",
  props: {
    title: {
      type: String,
      default: "title of header"
    }
  },
  data() {
    return {};
  },
  methods: {
    changeTitleHeader() {
      var data = {
        test: 'test --> data pass event varible',
        title: 'Change title in App.vue'
      }
      this.$emit('changeTitleEvent', data)
    }
  }
};
</script>

<style>
</style>