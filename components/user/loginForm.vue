<template>
  <el-form :model="form" ref="form" :rules="rules" class="form">
    <el-form-item class="form-item" prop="username">
      <el-input placeholder="用户名/手机" v-model="form.username"></el-input>
    </el-form-item>

    <el-form-item class="form-item" prop="password">
      <el-input placeholder="密码" type="password" v-model="form.password"></el-input>
    </el-form-item>

    <p class="form-text">
      <nuxt-link to="#">忘记密码</nuxt-link>
    </p>

    <el-button class="submit" type="primary" @click="handleLoginSubmit">登录</el-button>
  </el-form>
</template>

<script>
export default {
  data() {
    const validateUsername = (rule, value, callback) => {
      const isValid = /^1[3-9][0-9]{9}$/.test(value);
      if (!isValid) {
        callback(new Error("手机号格式错误"));
      } else {
        callback();
      }
    };
    return {
      // 表单数据
      form: {
        username: "13800138000",
        password: "123456"
      },
      // 表单规则
      rules: {
        username: [
          {
            //自定义校验函数
            validator: validateUsername,
            trigger: "blur"
          }
        ],
        password: [
          {
            required: true,
            message: "密码不能为空",
            trigger: "blur"
          }
        ]
      }
    };
  },
  methods: {
    // 提交登录
    handleLoginSubmit() {
      console.log(this.form);
      this.$refs.form.validate(valid => {
          if(valid){
              this.$axios({
                  url:'/accounts/login',
                  method: 'POST',
                  data: this.form
              }).then(res =>{
                  console.log(res)
                  const {data} = res;
                  //调用mutation的方法，把data存到store|vuex
                  this.$store.commit("user/setUserInfo", data)
              })
          }
      })
    }
  }
};
</script>

<style scoped lang="less">
.form {
  padding: 25px;
}

.form-item {
  margin-bottom: 20px;
}

.form-text {
  font-size: 12px;
  color: #409eff;
  text-align: right;
  line-height: 1;
}

.submit {
  width: 100%;
  margin-top: 10px;
}
</style>