<template>
  <div id="app">
    <transition name="message">
      <div v-if="showMessage" class="message">{{message}}</div>
    </transition>
    <input type="text" v-model="message">
    <button @click="showMessage = !showMessage">{{showMessage ? 'Hide Message' : 'Show Message'}}</button>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      message: "Sample Message",
      showMessage: false
    };
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
  position: relative;
  margin-top: 60px;
}
</style>
<style scoped>
.message {
  position: fixed;
  left: 50%;
  transform: translate(-50%, -50%);
  padding: 10px;
  background-color: #2c3e50;
  color: #FFF;
  border-radius: 5px;
  top: 30px;
}
.message-enter {
  top: 0;
}
.message-enter-active {
  transition: 0.5s;
}
.message-leave {
}
.message-leave-active {
  transition: 0.5s top;
  top: -30px;
}
</style>

