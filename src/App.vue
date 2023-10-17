<template>
  <div class="">
    <h1 style="text-align: center">My Blog</h1>
    <div
      class=""
      style="width: 80%; margin: 80px auto; display: flex; justify-content: space-between"
    >
      <BlogList :count-number="1" />

      <CounterComp />
    </div>

    <!-- <TRefs /> -->

    <!-- <ListComp style="margin-bottom: 1000px" />

    <button @click="toggle()">Toggle</button>
    <button @click="isToggled2 = !isToggled2">Toggle 2</button>
    <br />
    <br />
    <br />

    <button
      @click="isShown = false"
      @mouseover="isHovered = true"
      @mouseleave="isHovered = false"
      :style="isHovered ? 'background: green' : ''"
    >
      hide
    </button>

    <button v-if="!isHovered" @click="isShown = true">show</button>

    <div
      v-if="isShown && isToggled"
      class="div__default"
      style="
        background: black;
        display: flex;
        align-items: center;
        color: white;
        width: 200px;
        height: 80px;
      "
      :class="{ div__toggled: isToggled }"
      :style="[
        isToggled ? 'background: green; color: yellow;' : 'background: purple; color: white;',
        isToggled2 ? 'background: red;' : ''
      ]"
    >
      isToggled {{ isToggled }}
      <br />
      isToggled2 {{ isToggled2 }}
    </div> -->

    <!-- <div
      v-else-if="isShown && !isToggled"
      style="
        background: rgb(0, 30, 255);
        display: flex;
        align-items: center;
        color: red;
        width: 200px;
        height: 200px;
        border-radius: 50%;
      "
    ></div>

    <div
      v-else
      style="
        background: rgb(0, 246, 226);
        display: flex;
        align-items: center;
        color: red;
        width: 200px;
        height: 80px;
      "
    ></div> -->

    <!-- <h1 @click="hello">Hello Vue</h1> -->

    <!-- <h2>{{ firstName }}</h2>
    <br />
    <br />
    <h2 v-html="lastName"></h2>
    <br />
    <br />
    <h2>{{ lastName }}</h2>
    <br />
    <br />

    <h1>
      {{ 2 + 2 + lastName }}
    </h1>

    <div :id="oneDiv" class="">{{ calculateResult() }}</div> -->

    <CounterComp v-if="false" />
  </div>
</template>

<script>
import CounterComp from '@/components/CounterComp.vue'
import BlogList from '@/components/blog/BlogList.vue'
// import ListComp from '@/components/ListComp.vue'
// import TRefs from '@/components/TRefs.vue'

export default {
  name: 'App',
  components: {
    CounterComp,
    BlogList
    // ListComp,
    // TRefs
  },
  data() {
    return {
      firstName: 'My surename is <br/> Jhon',
      lastName: 'My surename is <br/> Smith',
      oneDiv: 'AnotherDiv',
      isToggled: false,
      isToggled2: false,
      isShown: false,
      isHovered: false
    }
  },
  mounted() {
    // oneFunction()
    // console.log(document.getElementById('oneDiv'))
    // console.log(document.getElementById(this.oneDiv))
    // console.log(document.getElementById('AnotherDiv'))
  },
  methods: {
    hello() {
      alert('hello')
    },
    calculateResult() {
      return 2 + 5 + 123 + 92034
    },
    toggle() {
      this.isToggled = !this.isToggled
    }
  }
}
</script>

<style>
h1 {
  color: green;
}

.div__default {
  border-radius: 10%;
}
button:hover {
  background: black;
}
.div__toggled {
  border-radius: 50%;
}
</style>
