<template>
  <div id="app">
    <div class="wrapper">
      <add-block/>
    </div>
  </div>
</template>

<script>
import AddBlock from "@/components/AddBlock";
export default {
  name: 'App',
  components: {
    AddBlock
  }
}
</script>

<style>
* {
  box-sizing: border-box;
}
#app {
  margin: 32px;
  font-family: "Source Code Pro", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background: rgba(255, 254, 251, 0.8);
  /*text-align: center;
  color: #2c3e50;
  margin-top: 60px;*/
}

.wrapper {
  display: flex;
  justify-content: left;
}

.item {
  width: 340px;
  padding: 25px;
  background: #FFFEFB;
  box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04), 0px 6px 10px rgba(0, 0, 0, 0.02);
  border-radius: 4px;
}

img {
  border-radius: 4px 4px 0 0;
  width: 100%;
}

</style>
