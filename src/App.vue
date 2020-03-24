<template>
  <div>
    <h1>Vue 3 demo</h1>
    <button @click="increment">{{ count }}</button>
  </div>
</template>

<script lang="ts">
  import { defineComponent, ref } from 'vue'

  import { Greeter } from './learning'

  export default defineComponent({
    setup (): object {
      // const state = reactive({
      //   count: 0
      // })

      // 看看ts
      class Greeter {
        greeting: string

        constructor (greet: string) {
          this.greeting = greet
        }

        @enumerable(true)
        doGreeting(): string {
          return this.greeting
        }
      }

      /*
      方法装饰器在运行时当作函数被调用，传入下列三个参数：
      1. 对于静态成员来说是类的构造函数，对于实例成员来说是类的原型对象
      2. 成员的名字
      3. 成员的属性描述符
      */

      function enumerable (value: boolean) {
        return function (target: any, propertyKey: string, descriptor: PropertyDescriptor) {
          console.log(target, propertyKey, descriptor)
          descriptor.enumerable = value

          console.log(descriptor)
        }
      }
      const greeterGdc = new Greeter('Guodongchao')

      console.log(greeterGdc.doGreeting())

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