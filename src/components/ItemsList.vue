<template>
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
</template>

<script>
export default {
  name: "ItemsList",
  components: {

  }
}
</script>

<style scoped>
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