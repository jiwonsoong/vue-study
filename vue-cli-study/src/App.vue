<template>
  <div>
    <!-- <app-header v-bind:프롭스 속성 이름="상위 컴포넌트의 데이터 이름"></app-header> -->
    <app-header v-bind:propsdata="str" v-on:renew="renewStr"></app-header>
  </div>
  <!-- template 안에는 root가 하나만 있어야 함! div가 병렬적으로 두 개 올 수 없음. -->
</template>

<script>
import AppHeader from './components/AppHeader.vue';

export default {
  name: 'App',
  data: function() {
    return {
      str: 'Header'
    }
  },
  components: {
    'app-header': AppHeader,
  },
  methods: {
    renewStr: function() {
      this.str = 'hi';
    }
  }
}
</script>

<style>

</style>