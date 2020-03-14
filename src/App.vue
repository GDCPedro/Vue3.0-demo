<template>
  <div>
    <h1>Vue 3 demo</h1>
    <button @click="increment">{{ count }}</button>
  </div>
</template>

<script>
  import { ref } from 'vue'

  export default {
    setUp() {
      const count = ref(0)

      const increment = () => {
        count.value++
      }

      return { count, increment }
    }
  }
</script>