<div align="center">

# 网腾无限AI - 安全教育与应急预案专家

**一个基于 Vue 3 + Vite + Vanilla CSS 构建的极简 AI 微应用，具备深色玻璃拟态自适应交互与微信端 H5 体验，专注安全生产隐患诊断与合规应急预案生成**

[Vue 3] · [TypeScript] · [Vite] · [Vanilla CSS] · [开源协议 MIT]

[![GitHub stars](https://img.shields.io/github/stars/WT-Agent/ai-anquan?style=social)](https://github.com/WT-Agent/ai-anquan)
[![GitHub license](https://img.shields.io/github/license/WT-Agent/ai-anquan)](https://github.com/WT-Agent/ai-anquan/blob/main/LICENSE)

[在线演示](#在线演示) · [快速启动](#快速启动) · [核心功能模块](#核心功能模块) · [AI 评估指标](#ai-评估指标) · [参与贡献](#参与贡献)

</div>

## 关于应用

网腾无限AI - 安全教育与应急预案专家是一款专为企业安全生产、高风险作业防护与突发事件处置打造的智能 AI 辅助工具。通过结合国家/行业安全标准（GB/AQ），为工矿制造、建筑施工、危险化学品、公共场所、交通运输等领域提供精准的隐患排查诊断、应急处置演练方案、PPE 防护装备清单及班前交底宣导指南。

团队成员均来自 C9 等顶尖学府，由在字节、腾讯、阿里的工程师组成，全职创业研发开源 AI 应用产品，让所有人感受 AI 的魅力。

本项目是网腾无限 AI 微应用的标准开发模版，内置了毛玻璃深色主题样式系统、移动端与 PC 端自适应响应式框架、API 中转代理配置与流量裂变逻辑。

**我们不搞概念，不卖课，只写能跑起来的代码。**

欢迎 Star、Fork、提 Issue，一起让这个项目变得更好用。

## 核心功能模块

1. **安全风险与隐患识别诊断**：深度剖析作业环境与具体工况，定位潜在重大危险源、习惯性违章与设备事故隐患。
2. **标准应急处置与疏散预案流程**：针对爆燃、泄漏、坍塌等突发状况，提供分级响应程序与人员疏散撤离路线指导。
3. **安全规范要点与防护装备清单**：明确强制执行的国家/行业安全生产标准（GB/AQ）及个人防护用品（PPE）配备要求。
4. **班前安全宣导与演练培训指南**：提供适合班组晨会口播的安全宣导要点与应急演练考核指标，降低现场作业事故率。

## AI 评估指标

本应用内置 5 大 AI 共识打分评估维度，全面校验方案的合规性与可操作性：

- **隐患识别精准度 (riskIdentification)**：评估对作业场景中风险源与事故隐患分析的全面性与准确度。
- **应急措施可行度 (emergencyFeasibility)**：评估应急响应流程与撤离指南在实际突发状况下的可操作性。
- **合规标准严谨度 (complianceStandard)**：校验方案引用的国家标准（GB）、行业规范（AQ）及 PPE 装备配备要求。
- **培训宣导通俗度 (trainingClarity)**：评估班前晨会宣导文本与演练指南的通俗易懂程度与落地效果。
- **响应处置时效性 (responseSpeed)**：评估应急预案各阶段响应时效与资源调配效率。

## 核心特性

- **极简自适应交互**：提供毛玻璃质感的深色玻璃拟态自适应 Web 界面，高度适配移动端 H5 微信浏览器与 PC 体验。
- **一键零成本部署**：纯静态前端结构，支持零成本部署于 Vercel、GitHub Pages 或 CDN/OSS 静态托管服务。
- **安全开发代理**：本地开发支持使用个人 API 密钥发起代理请求，密钥由 Vite 服务器中转，无需担心前端泄露。
- **裂变解锁与留存**：内置微信朋友圈扫码分享拦截与额度重置机制，提升流量转化与留存。

## 快速启动

### 1. 克隆项目
```bash
git clone https://github.com/WT-Agent/ai-anquan.git
cd ai-anquan
```

### 2. 安装依赖
项目强制使用 pnpm 作为包管理器：
```bash
pnpm install
```

### 3. 配置本地开发环境变量
复制并修改环境变量配置文件：
```bash
cp .env.example .env
```
根据微应用的功能类型，在 `.env` 中配置您的开发者密钥：
- `DEEPSEEK_API_KEY`: 您的 DeepSeek 开发者 API 密钥（用于文本生成任务）
- `DASHSCOPE_API_KEY`: 您的通义千问/通义万相开发者 API 密钥（用于多模态与生图任务）

### 4. 启动本地开发服务
```bash
pnpm dev
```
启动成功后在浏览器访问控制台输出的地址即可。

### 5. 生产构建打包
```bash
pnpm build
```
打包后生成的 `dist` 目录即为纯静态网页资源，可直接上传部署。

## 脚手架集成说明

本模板由私有总控仓库 `ai.wuxian.xyz` 中的 `@wuxian/cli` 脚手架统一管理，支持以下批量运维操作：

### 初始化或更新单个子项目

```bash
node bin/cli.js ai-anquan
```

脚手架将自动：
1. 读取子仓库的 `README.md` 首行作为 Prompt 主题。
2. 注入 Vue 3 静态页面结构及标准配置文件。
3. 保留原有的 `.git` 配置与 `README.md`，不覆盖个性化内容。

### 批量同步所有子项目

```bash
node bin/cli.js all
```

将模板的最新变更（如 SSO 逻辑、额度控制）一键同步至全部 31 个子项目。

### Agent 配置维护接口

```bash
# 读取子项目配置
node bin/cli.js get ai-anquan

# 写入/更新配置（支持热更新 prompt、model、title、temperature 等）
node bin/cli.js set ai-anquan prompt "你是一名国家注册安全工程师..."
node bin/cli.js set ai-anquan model deepseek-chat
```

## 联系方式

- GitHub Issues: [提交反馈](https://github.com/WT-Agent/ai-anquan/issues)
- 邮箱: us@wuxian.xyz

## 打赏支持

如果本项目对您有帮助，欢迎请作者喝杯咖啡。您的支持是持续维护与更新的动力。

<div align="center">

**微信支付** | **支付宝**
:---:|:---:
<img src="https://ai.wuxian.xyz/assets/tenpay.png" width="200" alt="微信支付"> | <img src="https://ai.wuxian.xyz/assets/alipay.png" width="200" alt="支付宝">

</div>

## 版权与许可

本项目基于 MIT License 开源协议。

Copyright (c) 2026. All rights reserved.
