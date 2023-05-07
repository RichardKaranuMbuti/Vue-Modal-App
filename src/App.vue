<template>
  <h1>{{ title }}</h1>
  <p>Welcome......</p>
  <div v-if="showModal">
    <Modal  theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Signup Now</a>
        <a href="#">More info</a>
      </template>
    <h1>Ninja Giveaway</h1>
    <p> Grab your Ninja swag for Half the price</p>
     </Modal>
  </div>

  <teleport to=".modals" v-if="showModaltwo">
    <Modal @close="toggleModaltwo">
    <h1>sign up for newsletter</h1>
    <p>For updates and promo codes</p>
     </Modal>
    </teleport>

  <button @click.alt="toggleModal">Open Model (alt)</button>
  <button @click="toggleModaltwo">Open Modeltwo </button>
  
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
      showModal: false,
      showModaltwo: false
    }
  },
  methods: {
    toggleModal(){
      this.showModal=!this.showModal
    },
    toggleModaltwo(){
      this.showModaltwo=!this.showModaltwo
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
