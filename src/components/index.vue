<script setup lang="ts">
import { ref } from 'vue';
import Dialog from './Dialog.vue';
import useCommandComponent from './useCommandComponent';

defineProps<{ msg: string }>();

const MyDialog = useCommandComponent(Dialog);

const showDialog = () => {
  MyDialog({
    title: '父组件弹窗',
    visible: true,
    onClose: () => MyDialog.close(),
  });
};
</script>

<template>
  <h3>click to open dialog</h3>
  <button @click="showDialog">open</button>
</template>

<style scoped></style>
