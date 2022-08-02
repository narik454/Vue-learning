<template>
  <posts-page/>
</template>

<script>
import PostsPage from "@/components/pages/PostsPage";

export default {
  name: 'App',
  components: {
    PostsPage
  }
}
</script>

<style>

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Source Sans Pro', sans-serif;
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 20px;
  color: #3F3F3F;
  background: rgba(239, 239, 237, 0.8);
}

img {
  border-radius: 4px 4px 0 0;
  width: 340px;
  height: 200px;
  object-fit: cover;
}

input {
  width: 100%;
  height: 40px;
  border-color: inherit;
  background: #FFFEFB;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  border-radius: 4px;
  padding: 10px 15px;
}

</style>
