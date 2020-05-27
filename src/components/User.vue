<template>
  <div class="user" v-if="user.active">
    <h4>user: {{ user.email }} , {{ text }}</h4>
    <button 
      class="detele"
      v-on:click="handleDelete"
    >
      Detele
    </button>
  </div>
</template>

<script>
export default {
  name: "user",
  data() {
    return {

    }
  },
  props: {
    text: {
      type: String,
      default: "not user"
    },
    user: {
      type: Object,
      default: null
    }
  },
  methods: {
    handleDelete(){
      var data = {
        id: this.user.id,
      }
      this.$emit('deteleUser', data)
    }
  }
};
</script>

<style>
  /* .user {
    position: relative;
  }
  .user .detele {
    position: absolute;
  } */
</style>