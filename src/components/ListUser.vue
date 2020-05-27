<template>
  <div>
    <h1>List User Component</h1>
    <div class="list-user">
      <user
        v-for="(item) in listUser"
        v-bind:key="item.id"
        v-bind:user="item"
        v-bind:text="text"
        v-on:deteleUser="deteleUser"
      />
    </div>
  </div>
</template>

<script>
import User from "./User";
export default {
  name: "list-user",
  data() {
    return {
      text: "user item"
    };
  },
  components: {
    User
  },
  props: {
    listUser: {
      type: Array,
      default: []
    }
  },
  methods: {
    deteleUser(data){
      this.$emit('deleteUserEvent', data)
    }
  }
};
</script>

<style>
.list-user {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}
.list-user .user {
  padding: 30px;
  margin-bottom: 30px;
  border: 1px solid #333;
  width: calc(33.3333% - 20px);
}
</style>