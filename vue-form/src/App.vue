<template>
  <form v-on:submit.prevent="submitForm">
    <div>
      <label for="username">id: </label>
      <input id="username" type="text" v-model="username">
    </div>
    <div>
      <label for="password">pw: </label>
      <input id="password" type="password" v-model="password">
    </div>
    <button type="submit">login</button>
  </form>
</template>

<script>
// 터미널에서 axios 설치: npm i axios
import axios from 'axios';

export default {
  name: 'App',
  data: function() {
    return {
      username: '',
      password: '',
    }
  },
  // data: 컴포넌트 단위로 개발할 때에는 컴포넌트 간 값의 참조가 일어나서 데이터가 공유되지 않도록 fucnction을 연결해서 새 객체를 return해주는 구문을 사용.
  methods: {
    submitForm: function() {
      // event.preventDefault();
      // form태그의 기본 동작은 새로고침이다. 어떤 정보를 제출하고 해당 페이지로 넘어가는 특성이 있기 때문에 이 새로고침을 막아주기 위해 event라는 인자를 받아서 event.preventDefault()를 써준다. 
      // 여기서 event는 위쪽 form태그 안에 적혀있는 'submit'이라는 event이다. 
      // 근데 이건 바닐라js 방식이고, vue에서는 form태그 안에 submit.prevent를 써서 해준다. 
      console.log(this.username, this.password);

      var url = 'https://jsonplaceholder.typicode.com/users';
      var data = {
        username: this.username,
        password: this.password
      }
      axios.post(url, data)
        .then(function(response) {
          console.log(response);
        })
        .catch(function(error) {
          console.log(error);
        });
      // axios는 http 프로토콜을 이용한 http 통신 라이브러리. 브라우저와 서버 간 데이터를 주고받기 위해 사용. 
      // post는 데이터를 생성하거나 조작할 때 사용.
      // url은 JSONPlaceholder라는 웹사이트에 있는 예시를 사용. 
    }
  }
}
</script>

<style>

</style>