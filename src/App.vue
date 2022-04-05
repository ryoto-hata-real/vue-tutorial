<template>
  <h1>{{ title }}</h1>
  <teleport to=".modals" v-if="showModal">
    <Modal theme="sale" @close="toggleShowModal">
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more info</a>
      </template>
        <h1>Ryoto Giveaway!</h1>
        <p>Grab your chance to the future</p>
      
    </Modal>
  </teleport>
  <teleport to=".modals"  v-if="showModalTwo">
    <Modal theme="sale" @close="toggleShowModalTwo">
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more info</a>
      </template>
        <h1>Ryoto Challange!</h1>
        <p>You dont have to fight!</p>
    </Modal>
  </teleport>
  <p>
    welcome...
  </p>
  <button v-on:click="toggleShowModal">
    Open Modal Giveaway
  </button>
  <button v-on:click="toggleShowModalTwo">
    Open Modal Challange
  </button>
  
</template>

<script>
import Modal from './components/Modal.vue'
export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: 'MY First Vue App :)',
      showModal: false,
      showModalTwo: false
    }
  },
  methods: {
    toggleShowModal(){
      this.showModal = !this.showModal
    },
    toggleShowModalTwo() {
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
h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
