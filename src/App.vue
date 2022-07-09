<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App" msg2="kakuninn" @parentMethod="onInputValue"/>

  <textarea v-model = "name"></textarea>
  <input type = "button" @click="onInputTextArea">
  <br>
 <span v-show="!validateEmail" class="text-warning" style="color:red">半角のみ入力してください</span>

  <br>

  <h1>親側データ：{{childData}}</h1>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',

data(){
  return{
    childData:null,
    name:null
  }
},
 computed: {
      validateEmail(){
        var pattern = /^\w+$/
        return pattern.test(this.name);
      }
      },

  components: {
    HelloWorld
  },
  methods:{
    onInputValue(data){
      this.childData = data

    },
    onInputTextArea(){
      this.name ="format"

    }
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
