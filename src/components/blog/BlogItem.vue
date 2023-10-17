<template>
  <div class="blog" :class="{ diabled: isDisabled }">
    <img class="img" src="" alt="" />

    <p class="title">{{ index }} {{ post.title }}</p>

    <p class="descr">{{ post.body }}</p>
  </div>
</template>

<script>
export default {
  props: {
    post: {
      type: Object,
      // default: () => {
      //   return {
      //     id: 1,
      //     userId: 1,
      //     body: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Exercitationem nam, aliquid ut',
      //     title: 'Title'
      //   }
      // }
      required: true
    },
    index: {
      type: String,
      // default: ''
      required: true
    },
    // isDisabled: {
    //   type: Boolean,
    //   default: false
    // }
    isDisabled: Boolean
  }
}
</script>

<style scoped>
.blog {
  margin-top: 40px;
  width: 100%;

  border-radius: 24px;
}
.img {
  width: 100%;
  height: 300px;
  background: #ccc;
  object-fit: cover;
}
.title {
  font-size: 24px;
  font-weight: bold;
  margin-top: 16px;
}

.descr {
  font-size: 16px;
  font-weight: normal;
  margin-top: 12px;
}
.blog.diabled .title {
  color: red;
}

.blog.diabled .descr {
  color: red;
}
</style>
