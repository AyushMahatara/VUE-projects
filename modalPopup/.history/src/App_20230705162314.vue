<template>
  <h1>{{ title }}</h1>
  <p>Welcome</p>
  <teleport to=".modals" v-if="showModal">
    <Modal @close="toggleModal">
      <h1>This is slot's modal</h1>
    </Modal>
  </teleport>

  <div v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <h1>Sign Up</h1>
      <p>read more</p>
    </Modal>
  </div>
  <button @click="toggleModal">Open Modal</button>
  <button @click="toggleModalTwo">Open Modal</button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "YO H0 H0 ",
      // header: "This is the Header",
      // content: "this is the content",
      showModal: false,
      showModalTwo: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo;
    },
  },
};
</script>

<style>
#app,
.modals {
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
