<template>
  <q-layout view="hHh lpR fFf">
    <q-header elevated class="bg-white text-grey-9" height-hint="98">
      <q-toolbar>
        <q-btn dense flat>
          <q-toolbar-title>
            <q-avatar>
              <img src="/logo.png" />
            </q-avatar>
            Happy Market
          </q-toolbar-title>
        </q-btn>
        <q-space />
        <q-btn stretch flat label="Home" to="/home" />
        <q-btn
          stretch
          flat
          label="리빙윈도"
          href="https://shopping.naver.com/living/homeliving/home"
          target="_blank"
        />
        <q-btn
          stretch
          flat
          label="푸드윈도"
          href="https://shopping.naver.com/fresh/traditionalalcohol/home"
          target="_blank"
        />
        <q-btn
          stretch
          flat
          label="장보기"
          href="https://shopping.naver.com/market/home"
          target="_blank"
        />
        <q-separator class="q-my-md q-mr-md" vertical />
        <q-btn
          unelevated
          rounded
          color="primary"
          label="로그인 / 회원가입"
          @click="openAuthDialog"
        />
      </q-toolbar>
    </q-header>
    <q-page-container :style="pageContainerStyles" class="bg-grey-3">
      <router-view />
    </q-page-container>
    <AuthDialog v-model="authDialog" />
  </q-layout>
</template>

<script setup>
import { computed, ref } from 'vue';
import { useRoute } from 'vue-router';

import AuthDialog from 'src/components/auth/AuthDialog.vue';

const route = useRoute();

const pageContainerStyles = computed(() => ({
  maxWidth: route.meta?.width || '1080px',
  margin: '0 auto',
}));

const authDialog = ref(true);
const openAuthDialog = () => (authDialog.value = true);
</script>
<style lang="scss" scoped></style>
