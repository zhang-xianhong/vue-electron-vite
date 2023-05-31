<template>
  <!-- <img alt="Vue logo" src="../assets/logo.png" /> -->
  <div>
    <div>
      一个基于VUE+VITE+ELECTRON+TS的脚手架模板
    </div>
    <div style="margin-top: 16px;">
      <button @click="openNewWin">新建窗口</button>
    </div>
  </div>
</template>
<script setup lang="ts">
import { useIpcRenderer } from "@vueuse/electron";
const ipcRenderer = useIpcRenderer();
const openNewWin = () => {
  ipcRenderer.send("window-new", {
    route: "/helloworld",
    width: 500,
    height: 500,
  });
};
</script>