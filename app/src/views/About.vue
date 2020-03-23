<template>
  <div class="about">
    <h1>This is an about page</h1>
    <h2>Message from state using Vuex: {{ title }}</h2>
    <form @submit.prevent="changeState()">
      <input type="text" v-model="text" placeholder="Text">
      <button type="submit">Change state!</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'About',
  computed: {
    title(){
      return this.$store.state.title
    }
  },
  methods:{
    changeState(){
      this.$store.state.title = this.text
    }
  }
}
</script>
