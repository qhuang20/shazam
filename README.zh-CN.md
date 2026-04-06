<p align="center">
  <img src="logo.svg" width="200" alt="Shazam logo"/>
</p>

<h1 align="center">SHAZAM! ⚡</h1>

<p align="center">一个让 Claude Code 真正变成你的软件工程搭档的插件。</p>

<p align="center">
  <a href="README.md">English</a> | 中文
</p>

不知道下一步做什么？大喊一声 **SHAZAM!** 它会告诉你。

## 为什么需要 Shazam？

Claude Code 很强，但它不会主动告诉你"接下来该做什么"。你需要自己记住该用哪个工具、什么顺序。

Shazam 解决了这个问题：**18 个 skill + 智能导航**，覆盖从需求到上线的完整工作流。每个 skill 完成后自动建议下一步——你只需要跟着走，或者随时喊 SHAZAM! 问路。

受 [superpowers](https://github.com/obra/superpowers) 启发，但更轻量：**软建议代替硬门控，没有 hook 注入，你始终掌控一切。**

## 三大核心工作流

### ⚡ 从零到一：规划新功能

```
/write-a-prd        → 通过访谈生成 PRD，提交为 GitHub Issue
/prd-to-plan        → 把 PRD 拆成阶段性实施计划
/prd-to-issues      → 把 PRD 拆成可独立认领的 GitHub Issues
/grill-me           → 压力测试你的任何方案
```

从一个模糊的想法开始，几轮对话后你就有了完整的 PRD、分阶段计划和可执行的 Issue 列表。

### ⚡ 让代码更好：架构改进

```
/improve-codebase-architecture   → 找出"浅模块"，提出深化方案
/request-refactor-plan           → 把重构拆成最小安全提交
/design-an-interface             → "Design It Twice"——并行对比 3+ 种设计
```

不是盲目重构，而是先诊断、再设计、再动手。每一步都有据可依。

### ⚡ 高效灭火：Bug 处理

```
/triage-issue      → 深入调查 root cause，生成 TDD 修复计划
/github-triage     → 批量分拣 Issue，标签状态机自动流转
/qa                → 口述 bug 就能自动建 Issue
```

从"这个按钮点了没反应"到"Issue 已建好，TDD 修复计划已附上"，全程自动。

## 更多 Skills

```
/ubiquitous-language             提取 DDD 领域术语表
/edit-article                    重构文章结构，提升清晰度
/git-guardrails-claude-code      拦截危险 git 命令
/setup-pre-commit                一键配置 Husky + Prettier
/migrate-to-shoehorn             测试中的 as 断言迁移
/scaffold-exercises              课程练习目录脚手架
/obsidian-vault                  Obsidian 笔记管理
```

## 安装

```bash
/plugin install shazam
```

或者手动安装：

```bash
git clone https://github.com/qhuang20/shazam.git ~/.claude/plugins/local/shazam
```

## 设计哲学

| | Superpowers | Shazam |
|--|------------|--------|
| 理念 | 强制纪律 | 智能引导 |
| 触发方式 | session hook 自动注入 | 用户主动喊 SHAZAM! |
| 流程控制 | 硬门控 + 铁律 | 软建议 + 自由选择 |
| 适合 | 团队规范化 | 个人开发者提效 |

**Shazam 的核心信念：好的工具应该是指南针，不是铁轨。**

## Credits

- Skills 基于 [mattpocock/skills](https://github.com/mattpocock/skills)
- 导航与 skill 链式衔接受 [obra/superpowers](https://github.com/obra/superpowers) 启发
