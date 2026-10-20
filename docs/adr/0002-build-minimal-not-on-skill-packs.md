# 不建在现有网文 skill 包上

状态：已接受（2026-10-20）

章枢不 fork、不依赖现有的网文 skill 包，从最小集自建，具体做法可以借用并注明出处。

## 背景

2026-10 调研 GitHub 上的同类项目：

- [oh-story-claudecode](https://github.com/zenstory-ai/oh-story-claudecode)（MIT，约 7.8k 星）：13 个 skill、7 个子 Agent、8 个 hook，追踪状态以一份 JSON 为唯一权威，从中渲染出各个视图。
- [webnovel-writer](https://github.com/lingfengQAQ/webnovel-writer)（GPL-3，约 7.6k 星）：合同与提交链、SQLite 与向量索引；v8 迁到 DeepSeek Harness。
- [chinese-novelist-skill](https://github.com/PenglongHuang/chinese-novelist-skill)（约 4k 星）：单个 skill，一次生成 10 到 50 章。

“文件当记忆”和一致性它们已经做好了：伏笔登记回收章，作者真相与读者已知分开记，没有细纲不写正文。它们的共同前提是 AI 推进流水线、作者在关口点头，所以作者一动手，系统就跟不上：

- webnovel-writer #77、#100：作者手改正文后，状态与正文脱节，没有重新同步的命令。
- oh-story 的派生追踪文件被手改，会被检查拒绝；它的作者记忆明确不从作者的修改中推断偏好。

规模也是问题：光 oh-story 的 hook 就有 8 个，接手的作者维护不了。

## 决定

- 不 fork、不依赖上述项目，从最小集自建。
- 可借的做法直接借，在对应 SOP 里注明出处。目前计划借用三项：百科条目区分已揭示和未揭示；没有章纲不起草；AI 腔句式的确定性扫描。
- 去 AI 味之类的通用能力，作者可以另装现成的 skill，章枢不打包。

## 后果

我们要重做一部分别人已经做好的记账工作。换来的是数据归属从第一天起就以作者的修改为一等输入，规模也小到作者能维护。以后如果发现某个现成 skill 正好补位，按 ADR 0001 的薄原则直接装上用，不吸收进本仓库。
