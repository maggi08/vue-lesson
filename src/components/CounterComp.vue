<template>
  <div class="">
    <h1>Count: {{ count }}</h1>

    <button @click="inc">Click to Count</button>
    <button @click="dec">Click to Decriment</button>
  </div>
</template>

<!-- <script setup>
import { ref } from 'vue'

let count = ref(0)

function inc() {
  count.value = count.value + 1
}
</script> -->

<script>
export default {
  name: 'CounterComp',
  data() {
    return {
      count: 10
    }
  },
  created() {
    console.log('Our component is created', this.count)
  },
  mounted() {
    console.log('Our component is mounted', this.count)
    this.inc()
  },
  methods: {
    inc() {
      this.count++
      this.log()
    },
    dec() {
      this.count--
      this.log()
    },
    log() {
      console.log('Counter now is - ', this.count)
    }
  }
}
</script>

<style scoped>
h1 {
  color: pink;
}
</style>
