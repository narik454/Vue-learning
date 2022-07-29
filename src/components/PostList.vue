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

      <post-item
          :key="post"
          v-for="post in posts"
          :post="post"
          @delete="deletePost"
          @transform="transformPost"
      />

    </div>

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
  },
  methods: {
    deletePost() {
      this.$emit('delete', this.posts);
    },
    transformPost() {
      this.$emit('transform', this.posts)
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