<template>
  <div class="px-4">
    hello
    <!-- <div class="" @click.self="parent">
      parent
      <div class="" @click="child1">child</div>
      <div class="" @click="child2">child2</div>
    </div> -->

    <!-- <button @keyup.enter="onSubmit">onSubmit</button>
    <form @submit.prevent="onSubmit">
      <button>onSubmit</button>
    </form> -->
    <!-- {{ value2 }}
    <input :value="value2" type="text" @keyup.enter="value2 = 'text2'" /> -->

    <!-- <h1 @mouseover="hovered = true" @mouseleave="hovered = false">Input hovered: {{ hovered }}</h1>

    <label
      class=""
      style="
        width: 200px;
        height: 60px;
        display: flex;
        align-items: center;
        justify-content: center;
      "
      :style="`background: ${activeBGColor}`"
    >
      <span>isToggled - {{ isToggled }}</span>
      <input v-model="isToggled" type="checkbox" />
    </label>

    <br />
    <br />
    <br />

    <label
      class=""
      style="
        width: 200px;
        height: 60px;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
      "
      :style="`background: ${activeBGColorForNumbers}`"
    >
      <span>number - {{ number }}</span>

      <input v-model="number" type="number" style="width: 50px; height: 20px" />
    </label> -->

    <!-- 
    <h2 id="">Value2 results - {{ value2 }}</h2>
    <input id="" :value="value2" v-on:input="onInput" /> -->

    <!-- <h1>List of Numbers</h1>

    <p>Can you show me all colors from array</p> -->

    <!-- <div class="" style="display: grid; grid-template-columns: 1fr 1fr">
      <p
        v-for="(color, index) in colors"
        :key="index"
        :style="`background: ${color}; color: white;`"
        class=""
      >
        {{ color }} {{ index }}
      </p>
    </div> -->

    <!-- <div v-for="(value, key) in user" :key="key" class="">{{ key }} {{ value }}</div>

    <h1>nameAndAge</h1>

    {{ user.name }} {{ user.age }}

    <br />

    {{ nameAndAge }} -->

    <!--<p>Can you show me numbers from 1 to 100</p>

    <p v-for="num in 100" :key="num">{{ num }}</p> -->
  </div>
</template>

<script>
export default {
  data() {
    return {
      hovered: false,
      number: 0,
      isToggled: false,
      value1: 'value1',
      value2: 'value2',
      value3: 'value3',
      user: {
        name: 'Magzhan',
        age: 23,
        nested: {
          name: 'Smith',
          age: 30
        }
      },
      progress: 10,
      colors: ['red', 'black', 'green', 'yellow', 'blue', 'purple', 'green', 'green', 'green']
    }
  },
  computed: {
    nameAndAge() {
      return `My name is ${this.user.name}, and I am ${this.user.age} years old`
    },
    activeBGColor() {
      // if (this.isToggled === true) return 'green'
      // return 'red'
      return this.isToggled ? 'green' : 'red'
    },
    activeBGColorForNumbers() {
      switch (this.number) {
        case 0:
        case 1:
        case 2:
        case 3:
          return 'red'
        case 4:
        case 5:
        case 6:
          return 'orange'
        default:
          return 'green'
      }
      // if (this.number < 3) return 'red'
      // if (this.number >= 3 && this.number < 6) return 'orange'
      // if (this.number >= 6 && this.number < 9) return 'purple'
      // return 'green'
    }
  },
  mounted() {
    setTimeout(() => {
      this.user.name = 'Koliya'
      this.user.age = 49
      this.value2 = 'text'
    }, 5000)
  },
  methods: {
    onInput(event) {
      console.log('onInput', event)
      this.value2 = event.target.value
    },
    alert() {
      alert('Hello')
    },
    parent() {
      console.log('parent')
    },
    child1() {
      console.log('child1')
    },
    child2() {
      console.log('child2')
    },
    onSubmit() {
      console.log('onSubmit')
    }
  }
}
</script>

<style scoped>
.px-4 {
  padding: 0 16px;
}
</style>
