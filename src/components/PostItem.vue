<template>
  <div
      @click="$emit('transform', post)"
      class="post"
      @mouseover="isHover = true"
      @mouseleave="isHover = false"
  >
    <div
        @click="$emit('delete', post)"
        v-show="isHover"
        class="delete-btn"
    ></div>
    <img class="post-image" :src="post.img" :alt="post.title">
    <h2 class="post-title">{{post.title}}</h2>
    <p class="post-description">{{post.description}}</p>
    <p class="post-price">{{post.price}} <span>руб.</span></p>
  </div>
</template>

<script>
export default {
  name: "PostItem",
  props: {
    post: {
      type: Object,
      required: true
    }
  },
  methods: {

  },
  data() {
    return {
      isHover: false
    }
  }
}
</script>

<style scoped>

.delete-btn {
  position: absolute;
  right: 0;
  content: url("@/assets/img/deleteIco.svg");
}

.post {
  position: relative;
  overflow: hidden;
  width: 340px;
  height: 400px;
  background: #FFFEFB;
  box-shadow: 0 20px 30px rgba(0, 0, 0, 0.04), 0 6px 10px rgba(0, 0, 0, 0.02);
  border-radius: 4px;
}

.post-title {
  margin: 10px 0;
  padding: 0 20px;
  font-weight: 600;
  font-size: 20px;
  line-height: 25px;
}

.post-description {
  padding: 0 20px;
  width: 340px;
  height: 140px;
  word-break: break-all;
  display: -webkit-box;
  -webkit-line-clamp: 7;
  -webkit-box-orient: vertical;
  overflow: hidden;
}

.post-price {
  padding: 0 20px;
  position: absolute;
  bottom: 10px;
}

</style>