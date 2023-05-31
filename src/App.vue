<template>
  <div class="app"></div>
</template>

<script setup lang="ts">
import * as event from "@tauri-apps/api/event";

event.listen("tauri://file-drop", (e) => {
  console.log("Tauri event", e);
});

event.listen("tauri://file-drop-hover", (e) => {
  console.log("Tauri event", e);
});

event.listen("tauri://file-drop-cancelled", (e) => {
  console.log("Tauri event", e);
});

// // 处理拖放区域的dragover事件
// function handleDragOver(event: DragEvent) {
//   event.stopPropagation();
//   event.preventDefault();
// }

// // 处理拖放区域的drop事件
// function handleFileSelect(event: DragEvent) {
//   event.stopPropagation();
//   event.preventDefault();
//   if (event.dataTransfer) {
//     for (const file of event.dataTransfer.files) {
//       console.log("Browser event", file.name, file.size, file.type);
//     }
//   }
// }
</script>

<style scoped>
.app {
  width: 100vw;
  height: 100vh;
  background-color: #efefef;
}
</style>
