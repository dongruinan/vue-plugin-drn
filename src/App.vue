<template>
  <div id="app">
    <img src="./assets/logo.png">
    <h2>{{newMsg}}</h2>
    <button @click="showToast">show toast</button>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      newMsg: 'vue-toast-c Demo'
    }
  },
  methods: {
    showToast() {
        this.$toast({mes: this.msg});
    }
  }
}
</script>
<style>
*{
  padding: 0;
  margin: 0;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 100px;
}
h2 {
  padding: 20px 0;
}
button{
  position: relative;
  color: #fff;
  background-color: #44cc8a;
  border: none;
  width: 80%;
  margin: 0 auto;
  display: block;
  font-size: 16px;
  height: 40px;
  margin-top: 10px;
  border-radius: 3px;
  outline: none;
  overflow: hidden;

}
button :after {
    content: "";
    display: block;
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    pointer-events: none;
    background-image: radial-gradient(circle, #fff 10%, transparent 10.01%);
    background-repeat: no-repeat;
    background-position: 50%;
    transform: scale(10, 10);
    opacity: 0;
    transition: transform .2s, opacity .5s;
  }

button :active:after {
    transform: scale(0, 0);
    opacity: .4;
    transition: 0s;
  }
</style>
