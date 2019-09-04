<template>
  <div class="wrapper">
    <i class="iconfont exit-icon">&#xe619;</i>
    <div class="login-wrapper">
      <div class="title">手机号登录</div>
      <div class="form-line">
        <i class="iconfont login-icon">&#xe72f;</i>
        <Input
          class="input-wrapper"
          v-model="phoneInput"
          type="text"
          placeholder="请输入手机号"
        />
      </div>
      <div class="form-line">
        <i class="iconfont login-icon">&#xe651;</i>
        <Input
          class="input-wrapper"
          v-model="pwdInput"
          type="password"
          placeholder="请输入密码"
        />
      </div>
    </div>
    <Button
      class="login-button"
      @click="handleLogin"
    >登录</Button>
  </div>
</template>

<script type="ts">
import Input from '@/components/Input'
import Button from '@/components/Button'

export default {
  components: {
    Input,
    Button
  },
  data() {
    return {
      phoneInput: '',
      pwdInput: ''
    }
  },
  methods: {
    handleLogin() {
    }
  }
}
</script>

<style lang="scss" scoped>
.wrapper {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  overflow: hidden;
  display: flex;
  flex-direction: column;
  .exit-icon {
    position: absolute;
    left: 10px;
    top: 10px;
    font-size: 24px;
  }
  .login-wrapper {
    margin-top: 120px;
    margin-left: 30px;
    .title {
      font-size: 28px;
      margin-bottom: 54px;
    }
    .login-icon {
      font-size: 28px;
    }
    .form-line {
      display: flex;
      align-items: center;
      margin-bottom: 32px;
    }
    .input-wrapper {
      margin-left: 20px;
    }
  }
  .login-button {
    width: 150px;
    height: 36px;
    margin-top: 40px;
    position: relative;
    left: 50%;
    transform: translateX(-50%);
    letter-spacing: 4px;
  }
}
</style>
