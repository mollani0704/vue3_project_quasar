<template>
  <div>
    <div class="text-h4">Home</div>
  </div>
  <div>{{ $route.name }}, {{ $route.meta }}</div>
</template>

<script setup></script>
<style lang="scss" scoped></style>
<route lang="yaml">
name: home-page
meta:
  requireAuth: true
</route>
