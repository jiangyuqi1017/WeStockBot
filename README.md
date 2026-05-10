# WeStockBot
# 📈 WeStockBot (个人股票情报推送机器人)

> 基于 GitHub Actions 的全自动金融情报系统。零成本、无需服务器、每天定时推送全球宏观指标与 A 股主力资金动向至微信。

[![Python](https://img.shields.io/badge/Python-3.9-blue)](https://www.python.org/)
[![GitHub Actions](https://img.shields.io/badge/GitHub-Actions-green)](https://github.com/features/actions)
[![License](https://img.shields.io/badge/license-MIT-green)](./LICENSE)

## 🚀 核心功能

WeStockBot 就像你的私人金融数据助理，利用 GitHub 免费的云端算力，每天在关键时间点自动运行：

1.  **🌞 宏观早报 (07:30)**
    * **全球市场**: 美股(纳指/标普)收盘数据、10年期美债收益率。
    * **风险风向**: 恐慌指数 (VIX)、离岸人民币汇率、黄金/白银/铜期货价格。
    * *价值：在 A 股开盘前，快速掌握外部环境风险。*

2.  **🌙 A股复盘 (16:30)**
    * **市场热度**: 全自动扫描今日领涨行业与热门概念板块。
    * **主力透视**: 基于数据清洗，计算今日**主力资金净流入**前三的板块。
    * *价值：收盘后用数据复盘，透过涨跌幅看资金真实动向。*

---

## 🛠️ 快速部署指南 (3步搞定)

你不需要懂代码，也不需要配置本地环境，只需要拥有一个 GitHub 账号。

### 第一步：Fork 本项目
点击页面右上角的 **Fork** 按钮，将本项目复制到你的 GitHub 账号下。

### 第二步：获取推送 Key
本项目使用 [Server酱](https://sct.ftqq.com/) 进行微信推送（免费且稳定）。
1.  登录 [Server酱官网](https://sct.ftqq.com/)，点击“SendKey”并复制 Key。
2.  回到你 Fork 后的 GitHub 仓库。
3.  点击顶部菜单栏的 `Settings` -> 左侧栏 `Secrets and variables` -> `Actions`。
4.  点击 `New repository secret` 按钮：
    * **Name**: 填写 `SERVERCHAN_KEY` (必须完全一致，不要有空格)
    * **Secret**: 粘贴你的 `SCT` 开头的 Key。
    * *注：如果你想同时推松给多人，可用英文逗号分隔多个 Key。*

### 第三步：启用自动运行
1.  点击仓库顶部的 `Actions` 标签。
2.  你会看到一个警告，点击绿色的 `I understand my workflows, go ahead and enable them` 按钮。
3.  **测试运行**：在左侧点击 `Daily Push`，右侧点击 `Run workflow` 按钮。如果你的微信收到了消息，说明部署成功！

---

## ⚙️ 进阶配置 (可选)

如果你想修改推送时间，可以编辑 `.github/workflows/` 目录下的文件：

* `daily_morning.yml`: 修改 `- cron: '30 23 * * 0-4'` (对应北京时间 07:30)
* `daily_evening.yml`: 修改 `- cron: '35 8 * * 1-5'` (对应北京时间 16:35)

*注意：GitHub Actions 的定时任务可能存在 5-15 分钟的延迟，属正常现象。*

## ⚠️ 免责声明

本项目仅供技术研究与编程学习交流使用。
* 所有数据均来自公开网络接口，不保证数据的准确性与实时性。
* **本项目不构成任何投资建议**。市场有风险，投资需谨慎。

