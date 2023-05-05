<template>
  <h1>{{ title }}</h1>
  <p>Welcome......</p>
  <div v-if="showModal">
    <Modal :header="header" :text="text" theme="sale" @close="toggleModal"/>
  </div>
  <button @click.alt="toggleModal">Open Model (alt)</button>
  
</template>

<script>
import Modal from './components/Modal.vue'


export default {
  components: { Modal },
  name: 'App',
  data(){
    return{
      title:'My first Vue App title',
      header:"sign up for the give away",
      text:"Grab your ninja swag for half the price",
      showModal: false
    }
  },
  methods: {
    toggleModal(){
      this.showModal=!this.showModal
    }
  }

}
  
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
