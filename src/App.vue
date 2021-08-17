<template>
  <h1>{{title}}</h1>
  <p>welcome...</p>
  <teleport to=".modals" v-if="showModal">
    <Modal theme="" @close="toggleModal">
      <template v-slot:Links>
        <a href="#">Sign up now</a>
        <a href="#">more info</a>
      </template>
      <h1>Ninja Giveaway!</h1>
      <p>Grab your ninja swag for half price!</p>
    </Modal>
  </teleport>

  <div v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <template v-slot:links>
        <a href="#">Buy now</a>
      </template>
      <h1>Winter Sales!</h1>
      <p>Grab your winter clothing for half price!</p>
    </Modal>
  </div>
  <button @click.alt="toggleModal">open modal (alt)</button>
  <button @click.shift="toggleModalTwo">open modal (shift)</button>
  <!-- <input type="text" ref="name">
  <button @click="handleClick">Click me</button> -->
</template>

<script>
// challenge
// - create an extra button to open  different modal
// - use the same modal component but pass in a different template (slot)
// - use a different method (e.g. toggleModalTwo) and data (e.g showModalTwo)
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data(){
    return {
      title: 'My First Vue App :)',
      showModal: false,
      showModalTwo: false
    }
  },
  methods: {
  //   handleClick(){
  //     console.log(this.$refs.name.classList.add('active'))
  //     this.$refs.name.focus()
  //   }
      toggleModal() {
        this.showModal = !this.showModal
      },
      toggleModalTwo() {
        this.showModalTwo = !this.showModalTwo
      }
  }
}
</script>

<style>
#app, .modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1{
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
