<template>
  <q-dialog
    :model-value="modelValue"
    @update:model-value="val => $emit('update:modelValue', val)"
    transition-show="none"
    transition-hide="none"
  >
    <q-card :style="{ width: '400px' }">
      <q-card-section class="flex">
        <q-space />
        <q-btn icon="close" flat round dense v-close-popup />
      </q-card-section>
      <q-card-section class="q-px-xl q-pb-xl">
        <SignInForm
          v-if="viewMode === 'SignInForm'"
          @change-view="changeViewMode"
        />
        <SignUpForm
          v-else-if="viewMode === 'SignUpForm'"
          @change-view="changeViewMode"
        />
        <FindPasswordForm v-else @change-view="changeViewMode" />
        <!-- <component
          :is="authViewComponents[viewMode]"
          @change-view="changeViewMode"
        /> -->
      </q-card-section>
    </q-card>
  </q-dialog>
</template>

<script setup>
import { defineAsyncComponent, ref } from 'vue';

import FindPasswordForm from './FindPasswordForm.vue';
import SignInForm from './SignInForm.vue';
import SignUpForm from './SignUpForm.vue';

// const authViewComponents = {
//   SignInForm: defineAsyncComponent(() => import('./SignInForm.vue')),
//   SignUpForm: defineAsyncComponent(() => import('./SignUpForm.vue')),
//   FindPasswordForm: defineAsyncComponent(() =>
//     import('./FindPasswordForm.vue'),
//   ),
// };

defineProps({
  modelValue: {
    type: Boolean,
    default: false,
  },
});

defineEmits(['update:modelValue']);

const viewMode = ref('SignInForm');
const changeViewMode = mode => (viewMode.value = mode);
</script>

<style lang="scss" scoped></style>
