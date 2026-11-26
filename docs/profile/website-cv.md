# 首页、CV 与平台简介的联动维护

整理日期：2026-11-26。本文件是对照与备用文案；本次整理没有替换公开首页或 CV 正文。

## 实际源文件

| 内容 | 唯一维护位置 |
| --- | --- |
| CV 任职、教育、技能、精选研究和论文 | [content/cv.md](../../content/cv.md) |
| 首页主文案 | [content/_index.md](../../content/_index.md) |
| 首页角色行、社交账号链接 | [hugo.yml](../../hugo.yml) |
| 正式论文完整列表 | [content/publications.md](../../content/publications.md) |
| 项目详细内容 | [content/projects/](../../content/projects/) |
| 内容与视觉规范 | [content-and-visual-guidelines.md](../content-and-visual-guidelines.md) |

CV 已在 Git 中保留历史，不另存一份需要手动同步的全文副本。

## 共同定位

- 当前公开网站主线：真实世界数据与 AI 生成的输出在什么条件下足以支持健康与可持续系统中的决策。
- 本资料库合并表述：从数据到决策的证据效度，强调测量、变量定义、误差、不确定性与验证。
- 两者关注同一条问题链。今后若更新首页或 CV Summary，核对两种表述是否仍相容，再决定是否替换；不要因整理备份而自动改站点正文。

## 首页 / CV Summary 备用短段

I am a Data Analyst at the University of Pittsburgh and a Statistician at the U.S. Department of Veterans Affairs through an IPA assignment. My work focuses on clinical research using real-world healthcare data. I study how measurement, variable definitions, and modeling choices affect the validity of scientific conclusions and decisions, drawing on my environmental engineering background and work in environmental sensing, energy, and sustainability systems.

## 已确认的 CV 结构

- 六项精选研究／项目；六篇精选论文，临床三篇、环境与能源三篇。
- 每段工作职责默认三条；Pitt Data Analyst 为两条直接职责加一条 VA IPA。
- IPA 用简短一段，不嵌套三个子项，不单独显示日期；CLEAR TEAM 只是其项目之一。
- CMU 的两阶段任职是 Research Associate（Oct–Dec 2025）、Research Associate II（Jan–Apr 2026）。共用三项职责：自适应采样、电力转型、太阳能项目结构。
- 石棉工作放在博士研究条目，描述具体方法与任务；不新增博士期间的 GRA 职位。
- 项目链接使用具体名称，如 Flight Delay Prediction Dashboard；不统一标成 Project。

## 每次更新时检查

1. 任职/学历变化：CV → [facts.md](facts.md) → LinkedIn Experience、ORCID、Scholar、各简介首句。
2. 研究主线变化：[positioning.md](positioning.md) → 各平台 About/Biography → 首页与 CV Summary。
3. 新论文正式发表：Papers、对应 Project、CV 精选项、LinkedIn Featured、ORCID Works、Scholar 条目。
4. 账号或 URL 变化：`hugo.yml`、facts、各平台互链。
5. 提交前核对改动范围；外部平台只有实际修改并核验后才记录“已同步”。
