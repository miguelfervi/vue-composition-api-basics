<template>
    <teleport to=".modals-container">
            <div class="modal" v-if="showModal">
                <h1>This is a modal</h1>
                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Itaque veritatis porro ea nemo debitis totam ab nisi saepe neque repellat repellendus fuga, ullam quod voluptatem cupiditate magnam error pariatur recusandae.</p>
                <button @click="showModal = false">Hide modal</button>
            </div>
        </teleport>
</template>


<style>
.modal {
    background: beige;
    padding: 10px;
    left: 0;
    top: 0;
    position: absolute;
    width: 100%;
    height: 100%;
    z-index: 1;
}
</style>