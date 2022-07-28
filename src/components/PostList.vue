<template>

  <div class="post-list">

    <div class="post-list__select">
      <select class="select-btn">
        <option>По умолчанию</option>
        <option>По алфавиту</option>
        <option>По цене</option>
      </select>
    </div>

    <div class="posts">

      <div class="post" :key="post" v-for="post in posts">
        <img class="post-image" :src="post.img" :alt="post.title">
        <h2 class="post-title">{{post.title}}</h2>
        <p class="post-description">{{post.description}}</p>
        <p class="post-price">{{post.price}} <span>руб.</span></p>
      </div>

    </div>

  </div>

</template>

<script>
export default {
  name: "PostList",
  props: {
    posts: {
      type: Array,
      required: true
    }
  }
}
</script>

<style scoped>

.post-list__select {
  display: flex;
  flex-direction: row-reverse;
  margin-bottom: 15px;
}

.select-btn {
  height: 36px;
  background: #FFFEFB;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  border-radius: 4px;
  font-weight: 400;
  font-size: 12px;
  line-height: 15px;
  color: #B4B4B4;
}

.posts {
  display: flex;
  flex-wrap: wrap;
  gap: 30px;
  flex-grow: 1;
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