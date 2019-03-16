<template>
  
    <div class="login">
             <el-form :model="form" :rules="rules"  status-icon label-width="30px">
                 <h2><strong>通用登录模版</strong></h2>
                 <h5>系统登录</h5>

                 <el-form-item   prop="username" >
                       <el-input v-model="form.username" placeholder="帐号">
                       <template slot="append"><i class="iconfont iconuser"></i></template>
                       </el-input>

                  </el-form-item>

                 <el-form-item width="100px">
                     <el-input type="password"  v-model="form.password" placeholder="密码">
                       <template slot="append"><i class="iconfont iconpassword"></i></template>
                       </el-input>
                  </el-form-item>


                   <el-form-item style="width:100%;" center>
                       <el-button style="width:100%;" type="primary">登 &nbsp  &nbsp 录</el-button>
                  </el-form-item>

             </el-form>

  </div>

</template>

<script>
export default {
   data() {
      return {
         value2:0,
         form:{username:'',         password:''},
         error:{hasError:false,msgError:''},
         okk:"ddf",
         rules:{
            username:[ { required: true, message: '用户名不能为空',trigger: 'blur' },
                  ]

         }
      };
    },
   methods:{
     goMain(){
         const params={
           username:this.form.username,
           password:this.form.password
         }
         this.$axios.post("/login",params
         ).then(res=>{

         }).catch(function(res){
           console.dir(res)
         })
     }
  }



}
</script>
<style scoped>
.login{
  background-color:#F5F5F5;
    margin: 8% auto;
    width:300px;
    padding: 40px 40px 15px 30px;
    border-radius: 10px;
    box-shadow: 0 2px 4px 0 rgba(0,0,0,.12), 0 0 6px 0 rgba(0,0,0,.04);
}

 .el-form{
   margin-top: 5px;
   width: 300px;
 }

.el-form-item{
  margin-top: 40px
}

h5{
  text-align: center;
  margin-top: 5px;
  margin-bottom: 20px;
}

h2{
  text-align: center
}

</style>

