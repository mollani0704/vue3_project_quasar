<template>
  <q-page padding>
    <div class="text-h4">커뮤니티 목록</div>
    <section class="q-gutter-y-sm q-mt-lg">
      <q-card v-for="id in 20" :key="id">
        <router-link :to="`/posts/${id}`">
          <q-card-section>{{ id }} 게시글</q-card-section>
        </router-link>
      </q-card>
    </section>
  </q-page>
</template>

<script setup></script>

<style lang="scss" scoped></style>
