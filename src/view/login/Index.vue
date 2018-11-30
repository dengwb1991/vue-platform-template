<!-- 登录 -->
<template>
  <div class="login-container">
    <Owl :closeEye="closeEye"/>
    <el-form class="login-form" label-position="left">
      <h3 class="title">vue-platform-template</h3>
      <el-form-item>
        <el-input v-model="loginForm.username"
                  name="username"
                  type="text"
                  placeholder="Username"
                  auto-complete="on"
                  clearable/>
      </el-form-item>

      <el-form-item>
        <el-input v-model="loginForm.password"
                  name="password"
                  type="password"
                  placeholder="Password"
                  auto-complete="on"
                  @focus="onFocus"
                  @blur="onBlur"
                  clearable/>
      </el-form-item>

      <el-form-item>
        <el-button type="primary"
                   class="sign-in">Sign in</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
import Owl from '@/components/Owl/Index'
export default {
  components: {
    Owl
  },
  data () {
    return {
      closeEye: false,
      userFocus: false,
      userError: false,
      loginForm: {
        username: null,
        password: null
      }
    }
  },
  methods: {
    onFocus () {
      this.closeEye = true
    },
    onBlur () {
      this.closeEye = false
    }
  }
}
</script>

<style type="text/css">
.login-container .el-input input {
  border: none;
  -webkit-appearance: none;
}
</style>

<style scoped>
.sign-in {
  width: 100%;
}
.login-form {
  position: absolute;
  left: 0;
  right: 0;
  width: 520px;
  max-width: 100%;
  padding: 35px 35px 15px 35px;
  margin: 120px auto;
}
.title {
  font-size: 26px;
  font-weight: 400;
  color: #eee;
  margin: 0px auto 40px auto;
  text-align: center;
  font-weight: bold;
}
.login-container {
  position: fixed;
  height: 100%;
  width: 100%;
  background-color: #2D3A4B;
}
</style>