<script setup lang="ts">
import { ref } from 'vue';

const props = defineProps<{ title: string; visible: boolean }>();
const emit = defineEmits(['close']);

const close = () => {
  emit('close');
};
</script>

<template>
  <div class="dialog" v-if="visible">
    <div class="mask"></div>
    <div class="content">
      <h3>{{ title }}</h3>
      <div>内容</div>
      <footer>
        <button @click="close">关闭</button>
      </footer>
    </div>
  </div>
</template>

<style scoped>
.dialog {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  .mask {
    position: absolute;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    background: #ccc;
    opacity: 0.8;
    z-index: -1;
  }
  .content {
    background: #fff;
    border-radius: 20px;
    padding: 20px;
    min-width: 300px;
    text-align: center;
  }
}
</style>
