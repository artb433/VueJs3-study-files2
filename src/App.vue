<template>
  <h1>{{title}}</h1>
  <p>Welcome......</p>
  <input type="text" ref="name">
  <button @click="handleClick">Click Here</button>
  <div v-if="showModal">
    <Modal theme='sale' @close="toggleModal">
      <template v-slot:links>
        <a href="#">Sign Up now</a>
        <a href="#">more info</a>
      </template>
      <h1>Ninja Giveaway!</h1>
      <p>Grab your ninja swag for half a price</p>
    </Modal>
  </div>
  <button @click="toggleModal">Open Modal</button>
</template>

<script>
import Modal from './components/Modal.vue' 

export default {
  name: 'App',
  data() {
    return {
      title: 'My Second Vue App',
      header: "Sign up for the Giveaway!",
      text: "Grab your ninja swag for half a price",
      showModal: false
    }
  },
  components: {
    Modal  
  },

  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    },
    handleClick() {
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
       
    },
    handleClose() {
      
      console.log('Modal closed')
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
input {
  width: 200px;
  height: 30px;
  border: 1px solid #ccc;
  border-radius: 5px;
  padding: 0 10px;
  margin: 10px 0;
}

h1 {
  border-bottom: 1px solid #ddd;

  padding-bottom: 10px;
}
</style>
