<template>
  <div>
    <div class="text-h4">게시글{{ $route.params.id }} 수정</div>
    <ul>
      <li>
        <router-link :to="`/posts/${$route.params.id}/edit`"
          >수정하기</router-link
        >
      </li>
    </ul>
  </div>
</template>

<script setup></script>

<style lang="scss" scoped></style>
