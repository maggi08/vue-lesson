<template>
  <div class="" :style="isCount15 ? 'background: black; color: white' : ''">
    <h1>Count: {{ count }}</h1>

    <button @click="inc">Click to Count</button>
    <button @click="dec">Click to Decriment</button>

    <br />
    <br />
    <br />

    {{ message }}

    <br />

    <div class="" :style="activeColor">
      <pre>
        {{ user }}
      </pre>
    </div>

    <!-- <input v-model="petName" type="text"> -->
  </div>
</template>

<script>
export default {
  name: 'CounterComp',
  data() {
    return {
      count: 10,
      user: {
        name: 'Jhon',
        pet: {
          name: 'Buldog'
        }
      },
      message: 'hello',
      isCount15: false
    }
  },
  computed: {
    activeColor() {
      return this.count > 15 ? 'background: green; color: red' : ''
    }
  },
  watch: {
    count(newValue, oldValue) {
      console.log('new value of count: ' + newValue + ', old value of count: ' + oldValue)
      if (newValue > 15) {
        this.isCount15 = true
      } else this.isCount15 = false
    },
    message: {
      handler(value, old) {
        console.log('new value of message: ' + value + ', old value of message: ' + old)
        alert(this.message)
      },
      immediate: true
    },
    // message(value, old) {
    //   console.log('new value of message: ' + value + ', old value of message: ' + old)
    //   alert(this.message)
    //   // this.log()
    // },
    user: {
      handler(newVal, oldVal) {
        console.log('User newVal', newVal)
        console.log('User oldVal', oldVal)
      },
      deep: true
    }
    // Это не лтрабатывает если меняется вложенные данные
    // user(newVal, oldVal) {
    //   console.log('User newVal', newVal)
    //   console.log('User oldVal', oldVal)
    // },
    // 'user.pet.name'(newVal, oldVal) {
    //   console.log('Pet name newVal', newVal)
    //   console.log('Pet name oldVal', oldVal)
    // }
  },
  created() {
    this.$watch('message', (newValue) => {
      console.log('message', newValue)
      // ...
    })

    // console.log('Our component is created', this.count)
  },
  mounted() {
    // console.log('Our component is mounted', this.count)

    setTimeout(() => {
      this.message = 'Good bye!'
      this.user.pet.name = 'Tima'
    }, 3000)

    // setTimeout(() => {
    //   // this.user.name = 'Yoda'

    //   this.user = 'This is user'
    // }, 5000)
  },
  methods: {
    inc() {
      this.count++
    },
    dec() {
      this.count--
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
