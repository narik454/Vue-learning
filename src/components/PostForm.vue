<template>

  <form class="create-post" @submit.prevent>

    <h1 class="create-post__title">Добавление товара</h1>

    <div class="create-post__inputs">

      <div>
        <h2>Наименование товара</h2>
        <input v-model="post.title" type="text" placeholder="Введите наименование товара">
      </div>

      <div>
        <h2>Описание товара</h2>
        <input v-model="post.description" type="text" placeholder="Введите описание товара">
      </div>

      <div>
        <h2>Ссылка на изображение товара</h2>
        <input v-model="post.img" type="url" placeholder="Введите ссылку">
      </div>

      <div>
        <h2>Цена товара</h2>
        <input v-model="post.price" type="number" placeholder="Введите цену" >
      </div>

      <button class="create-post__button" @click="createPost">Добавить товар</button>

    </div>

  </form>

</template>

<script>
export default {
  name: "PostForm",
  data() {
    return {
      post: {
        title: '',
        description: '',
        img: '',
        price: ''
      }
    }
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit('create', this.post);

      this.post = {
        title: '',
        description: '',
        img: '',
        price: ''
      };
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
  margin-bottom: 10px;
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
</style>