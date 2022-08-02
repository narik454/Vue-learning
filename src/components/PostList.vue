<template>

  <div class="post-list">

    <div class="posts" v-if="posts.length > 0">

      <post-item
          v-for="post in posts"
          :key="post.id"
          :post="post"
          @delete="$emit('delete', post)"
          @edit="$emit('edit', post)"
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
    },
    searchPost: {
      type: String
    }
  }
}
</script>

<style scoped>

.posts {
  display: flex;
  flex-wrap: wrap;
  gap: 30px;
}

</style>