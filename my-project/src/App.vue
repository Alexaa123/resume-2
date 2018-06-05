<template>
  <div id="app" v-bind:class="{negetive:classMode}">
    <Topbar class = 'Topbar'  v-on:preview="preview"/>
    <div id = 'main'>
      <Editor  v-bind:resume="resume" class = 'Editor' />
      <Preview v-bind:resume="resume" class = 'Preview'/>
      <el-button type="primary" id ='exitPreview' v-on:click="exitPreview">退出预览</el-button>
    </div>
    
    <!-- <img src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  </div>
</template>

<script>

import Topbar from './components/Topbar.vue'
import Editor  from './components/Editor.vue'
import Preview from './components/Preview.vue'

export default {
  name: 'app',
  components: {
    Topbar,Editor,Preview 
  },
  data(){
    return {
     classMode: false,
      resume:{
        profile:{
          name:'',
          city:'',
          birth:''},
        workhistry:[{company:'',time:''}],
        studyhistry:[{school:'',duration:'',degree:''}],
        awards:[{name:'',discription:''}],
        project:[{name:'',content:''}],
        contacts:{phone:'',email:'',QQ:'',github:''}
      }
    }
  },
  methods:{
    preview(){
       this.classMode = true
    },
    exitPreview(){
      this.classMode = false
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  
}
#main {
  display: flex;
  background: #ddd;
}
.Editor {
  width: 40%  ;
}
.Preview {
  flex: 1 ;
  height: 80%;
  margin: 16px 16px 16px 8px;
}
HTML,body, #app , #main {
  height: 100vh;
} 
#app {
  overflow: hidden;
}
.negetive .Topbar {
  display:none;
}
.negetive .Editor{
  display: none;
}
#exitPreview {
  display:none;
}
 .negetive #exitPreview {
  display:block;
  position:fixed;
  right: 16px;
  bottom: 65px;
} 
.negetive .Preview {
  max-width: 900px;
  margin: 0 auto;
  margin-top: 30px;
}
 




</style>
