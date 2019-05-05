<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home1</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view/>
  </div>
</template>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>

<script>
import Fingerprint2 from 'fingerprintjs2';
export default {
  data(){
    return{
      a:"app data a",
    }
  },
  created(){
    console.log("created");
    if (window.requestIdleCallback) {
      requestIdleCallback(function () {
          Fingerprint2.get(function (components) {
            console.log(components) // an array of components: y{key: ..., value: ...}
          })
      })
    } else {
      setTimeout(function () {
          Fingerprint2.get(function (components) {
            console.log(components) // an array of components: {key: ..., value: ...}
          })  
      }, 500)
    }
    // let aaa = "aaaa";
    let func = ()=>{
      this.a = "change a";

    };
    func();
  },
  mounted(){
    console.log("mouted");
    console.log(this.a);
  },
}
</script>

