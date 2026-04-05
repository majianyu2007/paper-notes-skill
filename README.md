# paper-notes-skill

一个用于生成论文阅读笔记的 OpenClaw skill。

## 目标

把用户提供的论文 PDF 作为主输入，结合可选代码仓库，产出可直接发布到博客的中文 Markdown 论文阅读笔记。

## 当前范围

- 以用户直接提供的 PDF 为主
- 支持 arXiv PDF 直链场景
- 不会因为只给标题就自动去找 PDF
- 可选分析论文对应代码仓库
- 默认不运行、不调试代码
- 代码分析不是必写项，只有有价值时才写
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
- `references/image-table-guidelines.md`  
  图表选择与裁剪规范
- `references/anti-ai-style-guide.md`  
  去 AI 味写作规范
- `references/failure-recovery.md`  
  失败恢复与兜底规则

## 打包

可用 OpenClaw 的打包脚本生成 `.skill` 文件。

示例：

```bash
python /home/majianyu/.nvm/versions/node/v24.14.1/lib/node_modules/openclaw/skills/skill-creator/scripts/package_skill.py /home/majianyu/.openclaw/workspace/paper-notes-skill /home/majianyu/.openclaw/workspace/paper-notes-skill/dist
```

## 已知边界

- 主输入仍然假设是论文 PDF，而不是任意论文网页
- 代码仓库分析默认是静态映射，不是复现工作流
- 若 PDF 提取质量很差，仍需依赖恢复流程修补理解

## 状态

已根据当前需求完成增强版技能定义。当前版本强化了：

- 分段生成而不是一次性整文生成
- 两轮验收
- 固定输出模板引用
- 分段生成工作流
- 反 AI 味和截图质量检查
- 独立终检清单
- 图表处理规范
- 去 AI 味写作规范
- 失败恢复与兜底规则
