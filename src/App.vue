<template>
  <div id="app">
    <img src="./assets/logo.png" />
    <!-- <router-view /> -->
    <button v-on:click="title = 'Ph Ng Tr Th'">Change title from Component App.vue</button>
    <div>{{ title }}</div>
    <comp-header 
      v-bind:title="title" 
      v-on:changeTitleEvent="handleChangeTitle"
    />
    <list-user 
      v-bind:listUser="listUser"
      v-on:deleteUserEvent="handleDeteleUser"
    />
    <demo-ref/>
    <demo-slot/>
    <comp-footer v-bind:title="title" />
  </div>
</template>

<script>
import CompHeader from './components/CompHeader';
import CompFooter from './components/CompFooter';
import ListUser from './components/ListUser';
import DemoRef from './components/DemoRef';
import DemoSlot from './components/DemoSlot'
export default {
  name: "App",
  data() {
    return {
      title: "heelo thinh",
      listUser: [
        { id: 1, email: "test1@gmail.com", active: true },
        { id: 2, email: "test2@gmail.com", active: true },
        { id: 3, email: "test3@gmail.com", active: true },
        { id: 4, email: "test4@gmail.com", active: true },
        { id: 5, email: "test5@gmail.com", active: true },
        { id: 6, email: "test6@gmail.com", active: true },
        { id: 7, email: "test7@gmail.com", active: true },
      ]
    }
  },
  components: {
    CompHeader,
    CompFooter,
    ListUser,
    DemoRef,
    DemoSlot,
  },
  methods: {
    handleChangeTitle(data){
      this.title = data.title;
      console.log('handleChangeTitle App.vue', data)
    },
    handleDeteleUser(data){
      const id_user_detele = data.id;
      this.listUser = this.listUser.filter(item => item.id !== id_user_detele)
      // var indexDelete = -1;
      // this.listUser.forEach((item, idx) => {
      //   if (item.id === id_user_detele){
      //     indexDelete = idx
      //   }
      // })
      // this.listUser.splice(indexDelete, 1)
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
