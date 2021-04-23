<template>
  <div class="register">
    <b-card title="注册">
    <b-form>
      <b-form-group>
        <b-form-input
          v-model="user.name"
          type="text"
          placeholder="请输入您的昵称(选填)"
        ></b-form-input>
      </b-form-group>
            <b-form-group>
        <b-form-input
          v-model="user.telephone"
          type="number"
          placeholder="请输入手机号码"
        ></b-form-input>
      </b-form-group>
            <b-form-group>
        <b-form-input
          v-model="user.password"
          type="password"
          placeholder="请输入密码"
        ></b-form-input>
      </b-form-group>
    </b-form>
    </b-card>
  </div>
</template>

<script>
export default {
  data() {
    return {
      user: {
        name: '',
        telephone: '',
        password: '',
      },
    };
  },
};
</script>
