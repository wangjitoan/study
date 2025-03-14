<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
  <Propstext text="我是props"/>
  <emitTest emittest=1 @emit-f="getEmit" v-model:modelValue="emitText" v-model:pagenum="pagenum" ref="emitRef"/>
  <br>
  <p>子组件输入内容:{{emitText}}</p>
  <p>子组件输入页数:{{pagenum}}</p>
  <p>{{ }}</p>
  <ullitest/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue' 
import Propstext from './components/propstext.vue';
import emitTest from './components/emitAndVmodel.vue';
import ullitest from './components/ullitest.vue';
import { createWebHistory } from 'vue-router';
import { ref, onMounted } from 'vue';
export default {
  name: 'App',
  components: {
    HelloWorld,
    Propstext,
    emitTest,
    ullitest
  },
  data(){
    return{
    msg:'我是data',
    emitText:'',
    pagenum:1,
    emitRef:null
  }
  },
  methods:{ getEmit(val){
    this.emitText=val
  }
},
setup(){
  const emitRef=ref()
  onMounted(() => {console.log(emitRef.value); })
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
