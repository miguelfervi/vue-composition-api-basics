<template>
  <div class="home">

    <h2>{{ appTitle }}</h2>

    <h3> {{ counterData.title }}</h3>

    <div>
      <button @click="decreaseCounter(2)" class="btn">--</button>
      <button @click="decreaseCounter(1)" class="btn">-</button>
      <span class="counter">{{ counterData.count }}</span>
      <button @click="increaseCounter(1)" class="btn">+</button>
      <button @click="increaseCounter(2)" class="btn">++</button>
    </div>

    <p>This counter is {{ oddOrEven }}</p>

    <div class="edit">
      <h4>Edit counter title: </h4>
      <input v-model="counterData.title" type="text">
    </div>

  </div>
</template>

<script setup>
import { reactive, computed, watch, onBeforeMount, onBeforeUnmount, onMounted, onUnmounted } from 'vue'

  const appTitle = 'My Amazing Counter App'
    // const counter = ref(0),
    //  counterTitle = ref('My Counter')

    const counterData = reactive({
      count: 0,
      title: 'My Counter'
    })

    watch(() => counterData.count, (newCount) => {
      if(newCount === 20) {
        alert('Way to go! You made it to 20')
      }
    })

    const oddOrEven = computed( () => {
      if(counterData.count % 2 === 0) return 'even'
      else return 'odd'
    })
    
    const increaseCounter = amount => {
      counterData.count += amount
    }

    const decreaseCounter = amount => {
      counterData.count -= amount
    }

    onBeforeMount(() => {
      console.log('onBeforeMount')
    }),

    onMounted(() => {
      console.log('Mounted')
    }),

    onBeforeUnmount(() => {
      console.log('Before Unmounted')
    }),

    onUnmounted(() => {
      console.log('Unmounted')
    })
</script>

<!-- <script>
export default {
  data() {
    return {
      count: 0
    }
  },
  computed: {
    myComputedProperty() {
      // perform logic based on a data property
      return 'myProperty'
    }
  },
  watch: {
    count(newCound, oldCount) {
      if(newCount == 20) alert('asasad')
    }
  },
  mounted() {
    // do something
  },
  unmonted() {

  }

}
</script> -->

<!-- <script>
import { ref } from 'vue'

export default {
  setup() {
    const counter = ref(0)
    
    const increaseCounter = () => {
      counter.value++
    }

    const decreaseCounter = () => {
      counter.value--
    }


    return {
      counter,
      increaseCounter,
       decreaseCounter
    }
  }
}
</script> -->

 <!-- <script>
export default {
  data() {
    return {
      counter: 0
    }
  },
  methods: {
    increaseCounter() {
      this.counter++
    },
    decreaseCounter() {
      this.counter--
    }
  }
}

</script> -->


<style>
  .home {
    text-align: center;
    padding: 20px;
  }

  .btn, .counter {
    font-size: 40px;
    margin: 10px;
  }

  .edit {
    margin-top: 60px;
  }
</style>