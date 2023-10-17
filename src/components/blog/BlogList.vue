<template>
  <div class="blog-list">
    <p class="title">Blog {{ countNumber }}</p>
    <BlogItem
      v-for="(item, index) in posts"
      :key="index"
      :post="item"
      :index="`Index: ${index}. `"
      :is-disabled="(index + 1) % 2 === 0"
    />
    <!-- :isDisabled="" -->
  </div>
</template>

<script>
import BlogItem from './BlogItem.vue'

export default {
  name: 'BlogList',
  components: {
    BlogItem
  },
  props: {
    countNumber: {
      type: Number,
      default: 1
    }
  },
  data() {
    return {
      posts: []
    }
  },
  mounted() {
    this.fetchPosts()
  },
  methods: {
    fetchPosts() {
      fetch('https://jsonplaceholder.typicode.com/posts')
        .then((res) => res.json())
        .then((res) => {
          console.log(res)
          this.posts = res
        })
        .catch((err) => {
          console.log(err)
        })
    }
  }
}
</script>

<style scoped>
.blog-list {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;

  width: 100%;
  max-width: 600px;
  margin: 40px auto;
}

.title {
  text-align: center;
}
</style>
