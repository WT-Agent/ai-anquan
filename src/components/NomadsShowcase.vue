<template>
  <section class="nomads-showcase-section">
    <div class="showcase-header">
      <div class="header-left">
        <h2 class="showcase-title">安全教育与应急演练实战模板库</h2>
        <p class="showcase-subtitle">精选典型安全隐患排查与应急响应场景，点击“一键套用”生成标准方案</p>
      </div>
      <span class="showcase-badge">已收录 {{ showcaseItems.length }} 个安全规范模板</span>
    </div>

    <div class="showcase-grid">
      <div 
        v-for="item in showcaseItems" 
        :key="item.id" 
        class="glass-card showcase-card"
      >
        <div class="card-header">
          <span class="scenario-tag">{{ item.tag }}</span>
          <span class="usage-count">{{ item.usageCount }} 次应用</span>
        </div>

        <div class="card-content">
          <h3 class="item-title">{{ item.title }}</h3>
          <p class="item-prompt">“{{ item.prompt }}”</p>
        </div>

        <div class="card-action">
          <button class="apply-btn" @click="applyTemplate(item)">
            <span>一键套用</span>
            <svg class="arrow-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
              <line x1="5" y1="12" x2="19" y2="12"></line>
              <polyline points="12 5 19 12 12 19"></polyline>
            </svg>
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { computed } from 'vue';

const emit = defineEmits<{
  (e: 'apply-template', payload: { prompt: string; scenario?: string; industry?: string }): void;
}>();

export interface ShowcaseItem {
  id: string;
  tag: string;
  title: string;
  prompt: string;
  scenario?: string;
  industry?: string;
  usageCount: string;
}

const showcaseItems = computed<ShowcaseItem[]>(() => [
  {
    id: 'anquan-1',
    tag: '危化品安全',
    title: '化工车间气体泄漏应急处置预案',
    prompt: '化工厂液氨储罐管道发生微小泄漏，需要一份包含警报触发、个人防护防护服穿戴、风向切断源及人员疏散的应急处置步骤。',
    scenario: '突发事件应急预案演练',
    industry: '危险化学品',
    usageCount: '28.6k'
  },
  {
    id: 'anquan-2',
    tag: '建筑施工',
    title: '高空作业防坠落与安全带交底',
    prompt: '针对 15 米高空钢结构搭建施工，制定班前五分钟安全教育宣导，强调双钩安全带系挂规则与脚手架搭设检查。',
    scenario: '施工作业与安全防护规程',
    industry: '建筑施工',
    usageCount: '34.2k'
  },
  {
    id: 'anquan-3',
    tag: '消防疏散',
    title: '商业综合体火灾人员逃生预案',
    prompt: '针对 5 层大型商场开展年度消防安全演练，拟定防烟面罩使用说明、防火卷帘门联动及多出口安全撤离路线指导。',
    scenario: '消防安全与疏散撤离',
    industry: '公共场所',
    usageCount: '41.8k'
  },
  {
    id: 'anquan-4',
    tag: '受限空间',
    title: '地下管网污水井下作业通风防毒',
    prompt: '市政污水井清淤作业，梳理“先通风、再检测、后作业”的标准规程，包含有毒有害气体检测仪操作与三脚架救援。',
    scenario: '企业安全生产与隐患排查',
    industry: '工矿制造',
    usageCount: '22.9k'
  },
  {
    id: 'anquan-5',
    tag: '机械加工',
    title: '金切机床旋转部件防缠绕排查',
    prompt: '车间数控车床与铣床隐患排查，制定防误触急停按钮、禁止戴手套操作、防护挡板完好性检查与违章罚款考核条款。',
    scenario: '企业安全生产与隐患排查',
    industry: '工矿制造',
    usageCount: '19.5k'
  },
  {
    id: 'anquan-6',
    tag: '交通防汛',
    title: '物流园区暴雨积水与物资转移',
    prompt: '物流仓库面临特大暴雨预警，编制沙袋防汛挡水板铺设、低洼处车辆移位及高压配电房防淹安全指南。',
    scenario: '突发事件应急预案演练',
    industry: '交通运输',
    usageCount: '31.4k'
  }
]);

function applyTemplate(item: ShowcaseItem) {
  emit('apply-template', {
    prompt: item.prompt,
    scenario: item.scenario,
    industry: item.industry
  });
}
</script>

<style scoped>
.nomads-showcase-section {
  margin-top: 2rem;
  width: 100%;
}

.showcase-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  margin-bottom: 1.25rem;
  padding-bottom: 0.75rem;
  border-bottom: 1px solid var(--card-border);
}

.showcase-title {
  font-size: 1.2rem;
  font-weight: 700;
  color: var(--text-primary);
  background: var(--primary-gradient);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.showcase-subtitle {
  font-size: 0.825rem;
  color: var(--text-secondary);
  margin-top: 0.25rem;
}

.showcase-badge {
  font-size: 0.75rem;
  color: #a5b4fc;
  background: rgba(99, 102, 241, 0.12);
  border: 1px solid rgba(99, 102, 241, 0.25);
  padding: 4px 10px;
  border-radius: 20px;
}

.showcase-grid {
  display: grid;
  grid-template-columns: repeat(1, 1fr);
  gap: 1.25rem;
}

@media (min-width: 640px) {
  .showcase-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 1024px) {
  .showcase-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}

.showcase-card {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 100%;
  padding: 1.25rem;
  background: rgba(255, 255, 255, 0.02);
  border: 1px solid var(--card-border);
  border-radius: 14px;
  transition: all 0.25s ease;
}

.showcase-card:hover {
  background: rgba(255, 255, 255, 0.05);
  border-color: rgba(99, 102, 241, 0.4);
  transform: translateY(-3px);
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.4);
}

.card-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 0.75rem;
}

.scenario-tag {
  font-size: 0.75rem;
  font-weight: 600;
  padding: 3px 8px;
  border-radius: 6px;
  background: rgba(168, 85, 247, 0.15);
  color: #c084fc;
  border: 1px solid rgba(168, 85, 247, 0.3);
}

.usage-count {
  font-size: 0.75rem;
  color: var(--text-secondary);
}

.card-content {
  margin-bottom: 1rem;
  flex: 1;
}

.item-title {
  font-size: 0.95rem;
  font-weight: 600;
  color: var(--text-primary);
  margin-bottom: 0.4rem;
}

.item-prompt {
  font-size: 0.825rem;
  color: var(--text-secondary);
  line-height: 1.45;
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
  font-style: italic;
}

.card-action {
  padding-top: 0.75rem;
  border-top: 1px solid rgba(255, 255, 255, 0.04);
}

.apply-btn {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 6px;
  padding: 0.5rem 1rem;
  background: rgba(99, 102, 241, 0.1);
  border: 1px solid rgba(99, 102, 241, 0.3);
  border-radius: 8px;
  color: #a5b4fc;
  font-size: 0.825rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.2s ease;
}

.showcase-card:hover .apply-btn {
  background: var(--primary-gradient);
  border-color: transparent;
  color: white;
}

.arrow-icon {
  width: 14px;
  height: 14px;
  transition: transform 0.2s ease;
}

.apply-btn:hover .arrow-icon {
  transform: translateX(3px);
}
</style>
