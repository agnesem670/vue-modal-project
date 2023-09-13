<template>
  <h1>{{ title }}</h1>
  <p>Welcome!</p>
  <div v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Sign up now</a>
        <a href="#">More info</a>
      </template>
      <h1>ninja Givaway</h1>
      <p>Hello ninja</p>
    </Modal>
  </div>
  <div v-if="showModalTwo">
    <Modal  @close="toggleModalTwo">
      <h1>modal two</h1>
      <p>Hello ninja</p>
    </Modal>
  </div>

  <button @click.alt="toggleModal">open modal (alt)</button>
  <button @click="toggleModalTwo">open modal two</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: 'My First Vue App',
      showModal: false,
      showModalTwo: false,
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
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.modal .actions {
    text-align: center;
    margin: 30px 0 10px 0;
}
.modal .actions a {
    color: #333;
    padding: 8px;
    border: 1px solid #eee;
    border-radius: 4px;
    text-decoration: none;
    margin: 10px;
}
.modal.sale {
    background: crimson;
    color: white;
}
.modal.sale h1 {
    color: white;
}
.modal.sale .actions {
    color: white;
}
.modal.sale .actions a {
    color: white;
}
</style>
