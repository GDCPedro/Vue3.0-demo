<template>
  <div>
    <h1>Vue 3 demo</h1>
    <button @click="increment">{{ count }}</button>
  </div>
</template>

<script lang="ts">
  import { defineComponent, ref } from 'vue'

  export default defineComponent({
    setup () {
      // const state = reactive({
      //   count: 0
      // })

      const count = ref(0)

      const increment = () => {
        console.log(count)
        count.value++
      }

      return { increment, count }
    }
  })
</script>