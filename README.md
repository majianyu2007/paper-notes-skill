# paper-notes-skill

一个用于生成论文阅读笔记的 OpenClaw skill。

## 目标

把用户提供的论文 PDF 作为主输入，结合可选代码仓库，产出可直接发布到博客的中文 Markdown 论文阅读笔记。

## 当前范围

- 以用户直接提供的 PDF 为主
- 支持 arXiv PDF 直链场景
- 可选分析论文对应代码仓库
- 输出固定模板的笔记成稿
- 要求分段生成、合并、至少两轮验收

## 目录结构

- `SKILL.md`  
  技能主说明
- `references/hard-requirements.md`  
  已确认的硬性规则与验收清单
- `references/article-template.md`  
  固定输出模板
- `references/staged-workflow.md`  
  分段生成工作流
- `references/review-checklist.md`  
  最终验收清单

## 打包

可用 OpenClaw 的打包脚本生成 `.skill` 文件。

示例：

```bash
python /home/majianyu/.nvm/versions/node/v24.14.1/lib/node_modules/openclaw/skills/skill-creator/scripts/package_skill.py /home/majianyu/.openclaw/workspace/paper-notes-skill /home/majianyu/.openclaw/workspace/paper-notes-skill/dist
```

## 状态

已根据当前需求完成增强版技能定义。当前版本强化了：

- 分段生成而不是一次性整文生成
- 两轮验收
- 固定输出模板引用
- 分段生成工作流
- 反 AI 味和截图质量检查
- 独立终检清单
