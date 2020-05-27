<template>
  <div class="comb-tabs">
    <div class="tabs-title">
      <span>{{ title }}</span>
      <ion-icon name="heart"></ion-icon>
    </div>
    <div class="tabs-content">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: 'comp-tabs',
  props: {
    title: {
      type: String,
      default: '',
    }
  },
  data() {
    return {

    }
  }
}
</script>

<style>
  .tabs-title {
    padding: 15px 10px;
    border: 2px solid greenyellow;
    display: flex;
    justify-content: space-between;
  }
  .tabs-content {
    border: 2px solid purple;
    margin-top: 10px;
    padding: 2px 2px;
  }
  .tabs-header {
    list-style-type: none;
    display: flex;
    margin: 0 0 5px 0;
    padding: 0px;
  }
  .tabs-header li {
    border: 1px solid orange;
    width: 100px;
    margin-right: 3px;
    text-align: left;
    padding: 5px;
    transition: all .5s ease;
    cursor: pointer;
  }
  .tabs-header li:hover {
    color: #fff;
    background-color: #333;
  }
  .tab-content {
    padding: 15px;
    border: 2px solid skyblue;
  }
</style>