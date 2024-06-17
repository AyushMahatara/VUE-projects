<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal">
      <slot> </slot>
      <!-- <h1>{{ header }}</h1>
      <p>{{ content }}</p> -->
    </div>
  </div>
</template>

<script>
export default {
  props: ["header", "content"],
  methods: {
    closeModal() {
      this.$emit("close");
    },
  },
};
</script>

<style>
.modal {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: white;
  border-radius: 10px;
}

.backdrop {
  top: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}

.modal h1 {
  color: #06ed38;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
