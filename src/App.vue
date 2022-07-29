<template>

  <div class="wrapper">
    <post-form
        @create="createPost"
    />
    <post-list
        @delete="deletePost"
        :posts="posts"
        @transform="transformPost"
    />
  </div>

</template>

<script>
import PostList from "@/components/PostList";
import PostForm from "@/components/PostForm";
export default {
  name: 'App',
  data() {
    return {
      posts: [
        {
          id: 1,
          title: 'Nazvanie',
          description: 'Opisanie',
          img: 'https://druzhniy-center.ru/wp-content/uploads/8/f/9/8f970e878337c2170713b4f20eafb065.jpeg',
          price: '10000'
        },

        {
          id: 2,
          title: 'Nazvanie 2',
          description: 'Opisanie 2',
          img: 'https://s1.1zoom.ru/b4344/471/Owls_Birds_Glance_537043_2560x1440.jpg',
          price: '1000'
        },

        {
          id: 3,
          title: 'Nazvanie 3',
          description: 'Opisanie 3',
          img: 'https://i.pinimg.com/originals/d2/ca/cf/d2cacf3d6f4f4bbf746c30084f95a41c.jpg',
          price: '100000'
        }
      ]
    }
  },
  components: {
    PostList, PostForm
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
    },
    deletePost(post) {
      this.posts.splice(post, 1);
      //this.posts = this.posts.filter(p => p.id !== post.id);
    },
    transformPost(post) {
      console.log(post);
    }
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

.wrapper {
  margin: 0 auto;
  padding: 30px;
  display: grid;
  grid-template-columns: 1fr 3fr;
  gap: 30px;
  width: 1570px;
}


</style>
