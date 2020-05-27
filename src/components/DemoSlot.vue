<template>
  <div class="demo-slot">
    <h1>Demo Slot</h1>
    <!-- <slot></slot> -->
    <comp-tabs title="Title Tab">
      <ul class="tabs-header">
        <li 
          v-for="(item, idx) in tabsHeader" 
          v-on:click="setActiveTab(idx)" 
          v-bind:key="idx"
          v-bind:class="{active: tabActive === idx + 1}"
        >
          {{ item.text }}
        </li>
      </ul>
      <div class="tab-content tab1" v-if="tabActive === 1">
        <p>Tab 1</p>
      </div>
      <div class="tab-content tab2" v-if="tabActive === 2">
        <p>Tab 2</p>
      </div>
      <div class="tab-content tab3" v-if="tabActive === 3">
        <p>Tab 3</p>
      </div>
    </comp-tabs>
  </div>
</template>

<script>
import CompTabs from './CompTabs';
export default {
  name: 'demo-slot',
  components: {
    CompTabs,
  },
  data() {
    return {
      tabsHeader: [
        { text: 'Tab 1' },
        { text: 'Tab 2' },
        { text: 'Tab 3' },
      ],
      tabActive: 1,
    }
  },
  methods: {
    setActiveTab(idx) {
      this.tabActive = idx + 1
    }
  }
}
</script>

<style>
  .demo-slot {
    margin-top: 100px;
    padding: 100px 30px;
    border: 1px solid #000;
  }
</style>