<template>
    <div class="modals">
        <h1>Modals</h1>
        <button @click="showModal = true">Show modal</button>
        <div class="modal" v-if="showModal">
            <h1>This is a modal</h1>
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Itaque veritatis porro ea nemo debitis totam ab nisi saepe neque repellat repellendus fuga, ullam quod voluptatem cupiditate magnam error pariatur recusandae.</p>
            <button @click="showModal = false">Hide modal</button>
        </div>
    </div>
</template>

<script setup>

import {ref} from 'vue'
const showModal = ref(false)
</script>

<style>
.modal {
    background: beige;
    padding: 10px;
}
</style>