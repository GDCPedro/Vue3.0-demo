<template>
  <div>
    <h1>Vue 3 demo</h1>
    <button @click="increment">{{ count }}</button>
  </div>
</template>

<script lang="ts">
  import { defineComponent, ref } from 'vue'

  export default defineComponent({
    setup (): object {
      // const state = reactive({
      //   count: 0
      // })

      const count: any = ref(0)

      // const increment = () => {
      //   console.log(count)
      //   count.value++
      // }

      function increment (): void {
        count.value++
      }

      return { increment, count }
    }
  })
</script>