<script setup lang="ts">
import { ref } from 'vue';
import Dialog from './Dialog.vue';
import useCommandComponent from './useCommandComponent';

defineProps<{ msg: string }>();

const MyDialog = useCommandComponent(Dialog);

const handleDialog = () => {
  MyDialog({
    title: '父组件弹窗',
    dialogVisible: true,
    onCancel: () => MyDialog.close(),
  });
};
</script>

<template>
  <h3>click to open dialog</h3>
  <button @click="handleDialog">open</button>
</template>

<style scoped></style>
