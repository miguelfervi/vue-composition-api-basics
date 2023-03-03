<template>
  <div class="modals">
    <h1>Modals</h1>
    <div>
      <label>
        Show dark modals?
        <input type="checkbox" v-model="showDarkModals" />
      </label>
    </div>
    <button @click="showModal = true">Show modal</button>
    <component
      v-model="showModal"
      :is="showDarkModals ? ModalDark : Modal"
      :userData="userData"
      title="My modal title (via prop)"
    >
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Itaque
        veritatis porro ea nemo debitis totam ab nisi saepe neque repellat
        repellendus fuga, ullam quod voluptatem cupiditate magnam error pariatur
        recusandae.
      </p>
    </component>
  </div>
</template>

<script setup>
import { ref } from "vue";
import Modal from "@/components/Modal.vue";
import ModalDark from "@/components/ModalDark.vue";


const showDarkModals = ref(false)
const showModal = ref(false);
</script>
