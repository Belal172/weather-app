<template>
  <HelloWorld />
  <button v-on:click="show=!show">toggle</button>
  <UnmountedComponent v-if="show"/>
  <FetchDataComponent/>

</template>

<script>
import UnmountedComponent from './components/UnmountedComponent.vue'
import FetchDataComponent from './components/FetchDataComponent.vue'
import HelloWorld from './components/HelloWorld.vue';
export default {
  name: 'App',
  components: {
   
    UnmountedComponent,
    FetchDataComponent,
    HelloWorld
  },
  data(){
    return{
      show:true
    }
  }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

  color: #2c3e50;
  margin-top: 60px;
}
</style>
