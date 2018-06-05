<template>
<div>
    <h2>{{title}}</h2>
    <div style="margin: 32px;"></div>
     <el-form :label-position="'top'" label-width="80px" :model="item" v-for="item in items" >
    <el-form-item v-for="(value,key,index) in item"  v-bind:label= "labels[index]" v-bind:key="key" v-bind:index="index">
        <el-input  v-model="item[key]" ></el-input>
    </el-form-item>
    <hr>
     <i class="el-icon-circle-close" v-on:click="removeItems"></i>
    </el-form>
    <el-button  id = "button" type="primary" v-on:click="addItems(index)">添加</el-button>
</div> 
</template>

<script>
export default {
    props:['items','title','labels'],
    data() {
      return {  
       
        }
      },
      computed:{
         keys(){
             return Object.keys(this.items[0])
         }
      },
      methods:{
          addItems(){
              const empty={}
              this.keys.map((key)=>{
                  empty[key] = ''
              })
               this.items.push(empty)
               

          },
          removeItems(index){
              this.items.splice(index,1)
          }
                }
}
</script>
<style>
    .el-form  {
        width: 300px;

    }
       
    
</style>





