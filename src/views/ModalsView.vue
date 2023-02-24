<template>
  <div class="modals">
    <h1>Modals</h1>
    <button @click="showModal = true">Show modal</button>
    <Modal
      v-model="showModal"
      title="My modal title (via prop)"
    >
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Itaque
        veritatis porro ea nemo debitis totam ab nisi saepe neque repellat
        repellendus fuga, ullam quod voluptatem cupiditate magnam error pariatur
        recusandae.
      </p>
    </Modal>
  </div>
</template>

<script setup>
import { ref } from "vue";
import Modal from "@/components/Modal.vue";
const showModal = ref(false);
</script>
