<template>
  <div class="px-4">
    <h1>List of Numbers</h1>

    <p>Can you show me all colors from array</p>

    <div class="" style="display: grid; grid-template-columns: 1fr 1fr">
      <p
        v-for="(color, index) in colors"
        :key="index"
        :style="`background: ${color}; color: white;`"
        class=""
      >
        {{ color }} {{ index }}
      </p>
    </div>

    <p>Can you show me numbers from 1 to 100</p>

    <p v-for="num in 100" :key="num">{{ num }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      colors: ['red', 'black', 'green', 'yellow', 'blue', 'purple', 'green', 'green', 'green']
    }
  }
}
</script>

<style scoped>
.px-4 {
  padding: 0 16px;
}
</style>
