<template>
  <div class="wrapper">
    <post-form
        :title="'Добавление товара'"
        :btn-name="'Добавить товар'"
        @create="createPost"
    />

    <div>

      <div class="post-list__select">
        <my-search
            v-model="searchInput"
        />
        <my-select
            v-model="selectedSort"
            :options="sortOptions"
        />
      </div>
      <post-list
          @delete="deletePost"
          :posts="sortedPosts"
      />
    </div>

  </div>
</template>

<script>
import PostList from "@/components/PostList";
import PostForm from "@/components/PostForm";
import MySelect from "@/components/UI/MySelect";
import MySearch from "@/components/UI/MySearch";

export default {
  name: 'PostPage',
  data() {
    return {
      posts: [
        {
          id: 1,
          title: 'А что это у тебя?',
          description: 'Камера',
          img: 'https://druzhniy-center.ru/wp-content/uploads/8/f/9/8f970e878337c2170713b4f20eafb065.jpeg',
          price: 10000
        },
        
        {
          id: 2,
          title: 'Ааа, я думала сова',
          description: '...',
          img: 'https://s1.1zoom.ru/b4344/471/Owls_Birds_Glance_537043_2560x1440.jpg',
          price: 1000
        },
        
        {
          id: 3,
          title: 'Сова',
          description: 'описание совы',
          img: 'https://i.pinimg.com/originals/d2/ca/cf/d2cacf3d6f4f4bbf746c30084f95a41c.jpg',
          price: 100000
        }
      ],
      selectedSort: undefined,
      searchInput: undefined,
      sortOptions: [
        {value: 'id', name: 'По умолчанию'},
        {value: 'price', name: 'По цене'}
      ]
    }
  },
  components: {
    PostList, PostForm, MySelect, MySearch
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
      this.updatePosts();
    },
    deletePost(post) {
      this.posts = this.posts.filter(p => p.id !== post.id);
      this.updatePosts();
    },
    updatePosts() {
      const json = JSON.stringify(this.posts);
      localStorage.setItem('posts', json);
    }
  },
  computed: {
    sortedPosts() {
      let posts = this.posts;
      if (this.searchInput) {
        posts = posts.filter(post => {
          console.log(post.title)
          return post.title.toLowerCase().includes(this.searchInput.toLowerCase())
        })
      }
      if (this.selectedSort) {
        posts = [...this.posts].sort((post1, post2) => {
          return post1[this.selectedSort] - post2[this.selectedSort]
        })
      }

      return posts
    }
  },
  mounted() {
    if (localStorage.getItem('posts')) {
      try {
        this.posts = JSON.parse(localStorage.getItem('posts'));
      } catch (e) {
        localStorage.removeItem('posts')
      }
    }
  }
}
</script>

<style scoped>

.post-list__select {
  display: flex;
  gap: 20px;
  margin-bottom: 15px;
}

.wrapper {
  margin: 0 auto;
  padding: 30px;
  display: grid;
  grid-template-columns: 1fr 3fr;
  gap: 30px;
}

</style>