<template>

  <div class="post-list">

    <div class="post-list__select">
      <select class="select-btn">
        <option>По умолчанию</option>
        <option>По алфавиту</option>
        <option>По цене</option>
      </select>
    </div>

    <div class="posts" v-if="posts.length > 0">

      <post-item
          :key="post.id"
          v-for="post in posts"
          :post="post"
          @delete="$emit('delete', post)"
          @transform="$emit('transform', post)"
      />

    </div>
    <h2 v-else style="color: black">
      Список постов пустой
    </h2>

  </div>

</template>

<script>
import PostItem from "@/components/PostItem";
export default {
  name: "PostList",
  components: {
    PostItem
  },
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
}

</style>