<template>
  <div class="">
    <input type="text" ref="customInput1" />
    <input type="text" ref="customInput2" />

    <button @click="clickMe">clickMe</button>

    <!-- <say-hello ref="sayHelloComp1" :number="1" />

    <SayHello ref="sayHelloComp2" :number="2" />

    <say-hello ref="sayHelloComp3" :number="3"></say-hello> -->

    <SayHello
      v-for="num in 14"
      :key="num"
      :ref="`sayHelloComp${num}`"
      :id="`sayHelloComp${num}`"
      :number="num"
    />
  </div>
</template>

<script>
import SayHello from './SayHello.vue'

export default {
  components: { SayHello },
  mounted() {
    // console.log(document.getElementById('customInput'))
    // document.getElementById('customInput')
    // console.log(this.$refs.customInput1)
    // let count = 0
    // setInterval(() => {
    //   count++
    //   console.log('interval', count)
    //   // if (count % 2 === 0) this.$refs.customInput1.blur()
    //   // else this.$refs.customInput1.focus()
    // }, 1000)
  },
  methods: {
    clickMe() {
      // console.log(this.$refs.sayHelloComp1)
      // console.log(this.$refs.sayHelloComp2)
      this.$refs.sayHelloComp1[0].say('Hello world')
      this.$refs.sayHelloComp2[0].say('Vue is cool')
      this.$refs.sayHelloComp3[0].say('You are cool guys')
      this.$refs.sayHelloComp4[0].say('Good bye')
    }
  }
}
</script>

<style></style>
