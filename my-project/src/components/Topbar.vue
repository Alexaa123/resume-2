<template>
  <div class = 'Topbar'>
      <p>Resume</p>
          <el-row class = 'button'>
            <el-button type="primary">登录</el-button>
            <el-button type="success">注册</el-button>
            <el-button type="info" v-on:click="preview">预览</el-button>          
      </el-row>
    

  </div>
    
</template>

<script>
export default {
    methods:{
        preview(){
            this.$emit('preview')
        }
    }
    
}
</script>

<style>
   
   .Topbar {
       position:relative;
      display: flex;
      justify-content: space-between;
      padding: 8px;
      text-align: center;
      box-shadow: 2px 3px 6px 4px rgba(0,0,0,0.4);
      z-index: 1;


   }
   .Topbar p {
       font-size: 24px;
       padding-left: 16px;
   }
   .Topbar .button {
       padding-top: 16px;
       padding-right: 16px;
   }

</style>
