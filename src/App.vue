<template>
  <h1>{{ title }}</h1>
  <p>welcome to the wanzo house</p>
  <div v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <h1>Sign up now for a 10% discount on your next order!</h1>
      <p>Grab some wanzo juice for a low low price!!!</p>
      <template v-slot:links>
        <a href="#">sign up</a>
        <br>
        <a href="#">more info</a>
      </template>
    </Modal>
  </div>
  <div v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <template v-slot:links>
        <a href="#">sign up</a>
        <br>
        <a href="#">more info</a>
      </template>
    </Modal>
  </div>
  <button @click="toggleModal">Open Modal One</button>
  <button @click="toggleModalTwo">Open Modal Two</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data () {
    return {
      title: 'wanzo',
      showModal: false,
      showModalTwo: false
    }
  },
  methods: {
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
  #app {
    text-align: center;
    margin: 400px auto;
  }

  h1 {
    color: aquamarine;
  }
</style>
