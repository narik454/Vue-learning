<template>

  <form
      class="create-post"
      @submit.prevent="checkForm"
  >

    <h1 class="create-post__title">Добавление товара</h1>

    <div class="create-post__inputs">

      <div>
        <h2>Наименование товара</h2>
        <input
            v-model="post.title"
            type="text"
            placeholder="Введите наименование товара"
        >
        <span class="error" v-show="!post.title && error">Поле является обязательным</span>
      </div>

      <div>
        <h2>Описание товара</h2>
        <input
            v-model="post.description"
            type="text"
            placeholder="Введите описание товара"
        >
      </div>

      <div>
        <h2>Ссылка на изображение товара</h2>
        <input
            v-model="post.img"
            type="url"
            placeholder="Введите ссылку"
        >
        <span class="error" v-show="!post.img && error">Поле является обязательным</span>
      </div>

      <div>
        <h2>Цена товара</h2>
        <input
            v-model.number="post.price"
            type="number"
            placeholder="Введите цену"
            min="0"
        >
        <span class="error" v-show="!post.price && error">Поле является обязательным</span>
      </div>

      <button
          type="submit"
          class="create-post__button"
          :class="{'create-post__button-active': isFilled}"
      >
        Добавить товар
      </button>

    </div>

  </form>

</template>

<script>
export default {
  name: "PostForm",
  data() {
    return {
      error: false,
      post: {
        title: null,
        description: null,
        img: null,
        price: null
      }
    }
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit('create', this.post);

      this.post = {
        title: undefined,
        description: undefined,
        img: undefined,
        price: undefined
      };
    },
    checkForm() {
      let formPost = this.post
      this.error = true;
      if (formPost.title && formPost.img && formPost.price) {
        this.error = false;
        return this.createPost();
      }
    }
  },
  computed: {
    isFilled() {
      return this.post.title && this.post.img && this.post.price
    }
  }
}
</script>

<style scoped>

.create-post {
  width: 400px;
  min-width: 400px;
}

.create-post__title {
  margin-bottom: 30px;
}

.create-post__inputs {
  width: 100%;
  padding: 25px;
  background: #FFFEFB;
  box-shadow: 0 20px 30px rgba(0, 0, 0, 0.04), 0 6px 10px rgba(0, 0, 0, 0.02);
  border-radius: 4px;
}

.create-post__inputs > div {
  padding-bottom: 30px;
  position: relative;
  display: block;
}

.create-post__inputs h2 {
  font-weight: 600;
  font-size: 12px;
  line-height: 13px;
}

.create-post__button {
  margin-top: 30px;
  width: 100%;
  height: 36px;
  background: #EEEEEE;
  border-radius: 10px;
  font-style: normal;
  font-weight: 600;
  font-size: 12px;
  line-height: 15px;
  text-align: center;
  letter-spacing: -0.02em;
  color: #B4B4B4;
  border-color: inherit;
}

.create-post__button-active {
  background: #2fc12f;
}

.error {
  padding-bottom: 15px;
  position: absolute;
  font-weight: 400;
  font-size: 12px;
  line-height: 10px;
  letter-spacing: -0.02em;
  color: #FF8484;
  bottom: 0;
  left: 0;
}

</style>