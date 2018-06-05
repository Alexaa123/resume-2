<template>
    <div class = 'Editor'>
        <nav>
            <ul>
                <li v-bind:class = "{active:currentTab === 0}">
                    <svg class="icon" aria-hidden="true" v-on:click="currentTab = 0">
                        <use  xlink:href="#icon-ID"></use>
                    </svg>
                </li>
                <li v-bind:class = "{active:currentTab === 1}">
                    <svg class="icon" aria-hidden="true" v-on:click="currentTab = 1">
                        <use xlink:href="#icon-work"></use>
                    </svg>
                </li>
                <li v-bind:class = "{active:currentTab === 2}">
                    <svg class="icon" aria-hidden="true" v-on:click="currentTab = 2">
                        <use xlink:href="#icon-read"></use>
                    </svg>
                </li>
                <li v-bind:class = "{active:currentTab === 3}">
                    <svg class="icon" aria-hidden="true" v-on:click="currentTab = 3">
                        <use xlink:href="#icon-prize"></use>
                    </svg>
                </li>
                <li v-bind:class = "{active:currentTab === 4}">
                    <svg class="icon" aria-hidden="true" v-on:click="currentTab = 4">
                        <use xlink:href="#icon-project"></use>
                    </svg>
                </li>
                <li v-bind:class = "{active:currentTab === 5}">
                    <svg class="icon" aria-hidden="true" v-on:click="currentTab = 5">
                        <use xlink:href="#icon-call"></use>
                    </svg>
                </li>
               
            </ul>
        </nav>
        
            <ul class = 'write-info'>
                <li v-bind:class = "{active:currentTab === 0}">
                   <ProfileEditor v-bind:profile = "resume.profile"/>
                </li>
                <li v-bind:class = "{active:currentTab === 1}">
                    <ItemEditor v-bind:items = "resume.workhistry" v-bind:title="'工作经历'"  v-bind:labels="['工作','时间']"/>  
                </li>
                <li v-bind:class = "{active:currentTab === 2}" >
                    <ItemEditor v-bind:items = "resume.studyhistry" v-bind:title="'学习经历'" v-bind:labels="['学校','时间','学位']"/>  
                </li>
                <li v-bind:class = "{active:currentTab === 3}">
                     <ItemEditor v-bind:items = "resume.awards" v-bind:title="'获奖经历'" v-bind:labels="['获奖名称','描述']"/> 
                    
                </li>
                <li  v-bind:class = "{active:currentTab === 4}">
                    <ItemEditor v-bind:items = "resume.project" v-bind:title="'项目经历'" v-bind:labels="['项目名称','项目内容']"/> 
                </li>
                <li v-bind:class = "{active:currentTab === 5}">
                    <h2>联系方式</h2>
                        <div style="margin: 32px;"></div>
                        <el-form :label-position="'top'" label-width="80px" :model="resume.contacts">
                        <el-form-item label="手机">
                            <el-input v-model="resume.contacts.phone"></el-input>
                        </el-form-item>
                        <el-form-item label="邮箱">
                            <el-input v-model="resume.contacts.email"></el-input>
                        </el-form-item>
                         <el-form-item label="QQ">
                            <el-input v-model="resume.contacts.QQ"></el-input>
                        </el-form-item>
                         <el-form-item label="GitHub">
                            <el-input v-model="resume.contacts.gitHub"></el-input>
                        </el-form-item>
                        </el-form>
                </li>
            </ul>

  </div>
</template>

<script>
import ProfileEditor from './ProfileEditor.vue'
import ItemEditor from './ItemEditor.vue'


export default {
    components:{
        ProfileEditor, ItemEditor
        },
    props:['resume'],
    data() {
      return {
        currentTab:0,
       
        }
      },
     
    }
  
   

</script>


<style>
     .icon {
         font-size: 40px;
         margin: 16px;
         color:white;
     }
     .Editor {
         display: flex;

     }
     nav {
         background: black;
     }   
     .write-info h2 {
         margin-top: 20px;
         margin-left: 40px;
     }
     .write-info form {
         margin-left: 32px;
     }
     .write-info li {
         display: none;
          box-shadow: 0 0 3px hsla(0, 0, 0, 0.5);
     }
    .write-info .active {
        display: block;
        margin-left: 12px;
        position:relative;
        z-index: 333;
       
        
    }
    nav .active {
        background-color: white;
    }
    nav .active .icon {
        color: black;
    }
    li  .el-form {
        position: relative;
    }
    .el-icon-circle-close {
        position: absolute;
        top: 0;
        right: 0;
    }
   #button {
     
       margin-left: 87px;
       margin-top: 5px;
   }
   .write-info {
       overflow:auto;
   }
</style>

