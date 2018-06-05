<template>
      <div class = 'Preview'>
            <section class='basic-info'>
            <h2>基本信息|BASICINFO</h2>
            <p>姓名：{{resume.profile.name||'请填写名称'}}</p>
            <p>城市：{{resume.profile.city||'请填写城市'}}</p>
            <p>出生年月：{{resume.profile.birth||'请填写生日'}}</p>
            <hr>
            </section>

            <section class = 'workhistry' v-if="filter(resume.workhistry).length >0" >
            <div style="margin: 32px;"></div>
            <h2>工作经历</h2>
            <ul v-for="work in filter(resume.workhistry)"  v-bind:work="work">
                  <li>
                        {{work.company||'公司名称'}}
                  </li>
                  <li>
                        {{work.time|| '在职时长' }}

                  </li>
            </ul>
            <hr>

            </section>
             <section class = 'sthdyhistry'  >
            <div style="margin: 32px;"></div>
            <h2> 学习经历</h2>
            <ul v-for="study in resume.studyhistry"  v-bind:study="study">
                  <li>
                      学校名称：{{study.school||'学校名称'}}
                   </li>
                   <li>
                      学习时间：{{study.duration|| '学习时间' }}
                   </li>
                  <li>
                      学位: {{study.degree|| '学位' }}
                  </li>    
            </ul>
            <hr>
            </section>
             <section class = 'awards' v-if="filter(resume.awards).length >0" >
            <div style="margin: 32px;"></div>
            <h2> 获奖经历</h2>
            <ul v-for="awards in filter(resume.awards)"  v-bind:awards="awards">
                  <li>
                        {{awards.name||'奖项名称'}}
                   </li>
                   <li>
                        {{awards.discription|| '奖项描述' }}
                  </li>
                 
            </ul>
            <hr>
            </section>
            <section class = 'project' v-if="filter(resume.project).length >0" >
            <div style="margin: 32px;"></div>
            <h2> 项目经历</h2>
            <ul v-for="project in filter(resume.project)"  v-bind:project ="project">
                  <li>
                        {{project.name||'项目名称'}}
                  </li>
                  <li>
                        {{project.content|| '项目内容' }}
                  </li>
            </ul>
            <hr>
            </section>
            <section class = 'contacts' >
            <div style="margin: 32px;"></div>
            <h2>联系方式</h2>
            <ul >
                  <li>
                        电话:{{resume.contacts.phone||'你的电话'}}
                  </li>
                  <li>
                         邮件：{{resume.contacts.email|| '邮件' }}
                  </li>
                  <li>
                        QQ：{{resume.contacts.QQ|| 'QQ' }}
                  </li>
                  <li>
                         GitHub：{{resume.contacts.GitHub|| 'GitHub' }}
                  </li>      
            </ul>
            <hr>
            </section>




      </div>
</template>

<script>
export default {
      props:['resume'],
     
      methods:{
        filter(array){
            return array.filter(item=> !this.isEmpty(item))
        },
        isEmpty(object){
            let empty = true
            for(let key in object){
                if(object[key]){
                    empty = false
                    break
                }
            }
            return empty
        }
    }
}
</script>


<style>
    .Preview {
       background-color: white ;      
       overflow: auto;
        position:relative;
        z-index: 333;
          box-shadow: 0 0 3px hsla(0, 0, 0, 0.5);
    }
    section {
          padding: 16px;
    }
        
</style>

