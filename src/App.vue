<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js + TypeScript App"/>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import useStore from '@/store';
import HelloWorld from './components/HelloWorld.vue';
import { AUTH_ACTION_TYPES } from './store/auth/actions';
import { AUTH_MUTATION_TYPES } from './store/auth/mutations';

export default defineComponent({
  name: 'App',
  components: {
    HelloWorld
  },
  setup() {
    const store = useStore()
    // store.dispatch(AUTH_ACTION_TYPES.LOGIN, '123')  // is error
    store.dispatch(AUTH_ACTION_TYPES.LOGIN,{ email: '123', password: '123'})  // is valid

    // store.commit(AUTH_MUTATION_TYPES.SET_TOKEN, 1) // is error
    store.commit(AUTH_MUTATION_TYPES.SET_TOKEN, '1') // is valid
  }
});
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
