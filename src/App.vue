<template>
  <div id="app">
    <img width="25%" src="./assets/logo.png">

    <div class="group">
      <button>default</button>
      <button disabled>default</button>
    </div>
    <div class="group">
      <Button>button</Button>
      <Button disabled>disabled</Button>
    </div>
    <div class="group">
      <Button
        border-color="rebeccapurple"
        background="#fff"
        color="rebeccapurple"
        mouse-over-background="rebeccapurple"
        mouse-over-color="#fff"
      >button</Button>
      <Button
        border-color="green"
        background="green"
        color="#fff"
        mouse-over-background="#fff"
        mouse-over-color="green"
      >button</Button>
    </div>

    <div class="group">
      <Button
        corner="5"
        padding="25"
        border-color="crimson"
        background="#fff"
        color="crimson"
        mouse-over-background="crimson"
        mouse-over-color="#fff"
      >button</Button>
      <Button
        corner="5"
        :padding="205"
        border-color="orange"
        background="orange"
        color="#fff"
        mouse-over-background="#fff"
        mouse-over-color="orange"
      >button</Button>
    </div>
  </div>
</template>

<script>
import Button from "./components/Button";

export default {
  name: "App",
  components: {
    Button
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.group {
  margin: 10px;
  color: blueviolet;
}
</style>
