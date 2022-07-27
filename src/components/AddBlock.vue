<template>

  <div class="head">

    <div class="add-block">

      <div class="add-block__header">
        <h1 class="add-block__title">Добавление товара</h1>
      </div>

      <div class="add-block__main">

        <div>
          <h2>Наименование товара</h2>
          <input v-model="addBlock.name" type="text" placeholder="Введите наименование товара">
        </div>

        <div>
          <h2>Описание товара</h2>
          <input v-model="addBlock.desc" type="text" placeholder="Введите описание товара">
        </div>

        <div>
          <h2>Ссылка на изображение товара</h2>
          <input v-model="addBlock.img" type="url" placeholder="Введите ссылку">
        </div>

        <div>
          <h2>Цена товара</h2>
          <input v-model="addBlock.price" type="number" placeholder="Введите цену" >
        </div>

      </div>

      <div class="add-block__footer">
        <button @click="objItem" class="button">Добавить товар</button>
      </div>

      <p>{{addBlock}}</p>

    </div>

    <div class="app__items">

      <div class="filter">
        <button>По умолчанию</button>
      </div>

      <div class="items-list">

        <div class="item">

          <img src="../assets/img/img1.jpg" alt="img">

          <div>
            <h2></h2>
            <p>Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк</p>
          </div>

          <p> <span>руб.</span></p>

        </div>

      </div>

    </div>

  </div>

</template>

<script>
export default {
  name: "AddBlock",
  data() {
    return {
      addBlock: {
        name: '',
        desc: '',
        img: '',
        price: ''
      }
    }
  },
  methods: {
    objItem: function () {
      return this.addBlock;
    }
  }
}
</script>

<style scoped>

  .head {
    display: flex;
    flex-grow: 1;
  }

  .add-block {
    max-width: 340px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    flex-grow: 1;
  }

  .add-block__main {
    width: 100%;
    padding: 25px;
  }

  input {
    width: 100%;
    height: 40px;
  }

  h2 {
    font-weight: 600;
    font-size: 12px;
    line-height: 13px;
  }

  .add-block__footer {
    width: 100%;
    padding: 25px;
  }

  .button {
    border-radius: 10px;
    width: 100%;
    height: 40px;
    border-color: white;
  }

  button {
    height: 36px;
    background: #FFFEFB;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
    border-radius: 4px;
    border-color: white;
  }

  .filter {
    text-align: right;
  }

  .app__items {
    flex-grow: 1;
  }

  .items-list {
    display: flex;
    gap: 50px;
  }
</style>