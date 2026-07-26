<template>
  <div class="glass-card ticker-card">
    <div class="ticker-wrapper">
      <div v-for="(item, index) in tickerItems" :key="index" class="ticker-item">
        <span>{{ item.text }}</span>
        <span style="color: var(--success-color); font-weight: bold;">[预案生成完成]</span>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const tickerItems = ref([
  { text: '用户 138****9102 完成了化工车间危化品泄漏应急处置预案' },
  { text: '用户 177****4821 完成了施工现场高空作业防坠落安全交底' },
  { text: '用户 189****3309 完成了高层建筑火灾逃生疏散与应急演练指南' },
  { text: '用户 131****8876 完成了特种设备安全隐患排查与整改清单' },
  { text: '用户 153****1290 完成了机械加工班组班前安全宣导指导' },
]);
</script>
