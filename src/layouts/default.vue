<template>
  <q-layout view="lHh Lpr lff" class="bg-grey-2">

    <q-header bordered class="bg-white text-grey-9">
      <q-toolbar>
        <q-btn flat dense to="/">
          <q-toolbar-title>
            <span class="logoTitle">COMMUNITY</span>
          </q-toolbar-title>
        </q-btn>

        <q-toolbar-title />

        <q-btn stretch flat label="Home" to="/home"/>
        <q-btn stretch flat label="수강하기" href="https://google.com" target="_blank"/>
        <q-btn stretch flat label="온라인강의" href="https://edu.gymcoding.co" target="_blank"/>
        <q-btn stretch flat label="유튜브" href="https://youtube.com/@gymcoding" target="_blank"/>

        <q-separator class="q-my-md q-mr-md" vertical />
        <q-btn unelevated rounded color="primary" label="로그인 / 회원가입" @click="openAuthDialog"/>

      </q-toolbar>
    </q-header>

    <q-page-container :style="pageContainerStyles">
      <router-view />
    </q-page-container>

    <AuthDialog v-model="authDialog"/>
  </q-layout>
</template>

<script setup>
import { computed, ref } from 'vue';
import { useRoute } from 'vue-router';

import AuthDialog from 'src/components/auth/AuthDialog.vue';

  const route = useRoute();

  console.dir(route);
  const pageContainerStyles = computed(() => (
    {maxWidth: route.meta?.width || '1080px', margin: '0 auto'}
  ));

  const authDialog = ref(true);
  const openAuthDialog = () => {authDialog.value = true}
</script>

<style>
</style>


