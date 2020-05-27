<template>
  <div>
    <h1>Footer Component</h1>
    <h3>{{ title }}</h3>
  </div>
</template>

<script>
export default {
  name: "footer-component",
  data() {
    return {}
  },
  props: {
    title: {
      type: String,
      default: "hello world"
    }
  }
};
</script>

<style></style>
