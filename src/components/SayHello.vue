<template>
  <div class="">{{ number }} - {{ message }}</div>
</template>

<script>
export default {
  data() {
    return {
      message: 'nothing'
    }
  },
  props: {
    number: {
      type: Number,
      default: 0
    }
  },
  methods: {
    say(value) {
      console.log('say', value)
      this.message = value
    }
  }
}
</script>

<style></style>
