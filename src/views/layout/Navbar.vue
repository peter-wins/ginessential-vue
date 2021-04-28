<template>
  <div>
    <b-navbar
      toggleable="lg"
      type="dark"
      variant="info"
    >
      <b-container>
        <b-navbar-brand @click="$router.push({name: 'Home'})">OceanLearn</b-navbar-brand>

        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
        <b-collapse
          id="nav-collapse"
          is-nav
        >

          <!-- Right aligned nav items -->
          <b-navbar-nav class="ml-auto">
            <b-nav-item-dropdown
              right
              v-if="userInfo"
            >
              <!-- Using 'button-content' slot -->
              <template #button-content>
                <em>{{userInfo.name}}</em>
              </template>
              <b-dropdown-item href="#">个人主页</b-dropdown-item>
              <b-dropdown-item href="#">登出</b-dropdown-item>
            </b-nav-item-dropdown>

            <dev v-if="!userInfo">
              <b-nav-item
                v-if="$route.name != 'login'"
                @click="$router.replace({name: 'login'})"
              >登录</b-nav-item>
              <b-nav-item
                v-if="$route.name != 'register'"
                @click="$router.replace({name: 'register'})"
              >注册</b-nav-item>
            </dev>

          </b-navbar-nav>

        </b-collapse>
      </b-container>
    </b-navbar>
  </div>
</template>

<script>
import { mapState } from 'vuex';
// import storageService from '@/service/storageService';

export default {
  computed: mapState({
    userInfo: (state) => state.userModule.userInfo,
  }),
  // computed: {
  //   userInfo() {
  //     return JSON.parse(storageService.get(storageService.USER_INFO));
  //   },
  // },
};
</script>
<style lang="scss">
</style>
