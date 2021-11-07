<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <!-- 컴포넌트 명명법 종류 -->
    <!-- <hello-world></hello-world> -->
    <!-- <HelloWorld></HelloWorld> -->
    <!-- <HelloWorld/> -->
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
// ☆ 컴포넌트의 내용을 들고와서 컴포넌트에 연결해서 사용한다. 

export default {
  // 인스턴스 옵션 속성 or 컴포넌트 옵션 속성
  name: 'App',
  components: {
    HelloWorld,
    // 'hello-world': HelloWorld,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
