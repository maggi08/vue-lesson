<template>
  <div class="">
    <h1 v-on:click="hello">Hello Vue</h1>

    <CounterComp />
  </div>
</template>

<script>
import CounterComp from '@/components/CounterComp.vue'

export default {
  name: 'App',
  components: {
    CounterComp
  },
  mounted() {
    // oneFunction()
  },
  methods: {
    hello() {
      alert('hello')
    }
  }
}
</script>

<style>
h1 {
  color: green;
}
</style>
