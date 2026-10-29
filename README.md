# 工业 AI 研究周报与学习课程
公开网站：https://daniel-netsecu.github.io/industrial-ai-study/

## OpenClaw 接入与执行规则
先读 [AGENTS.md](AGENTS.md) 和 [RULES.md](RULES.md)。完整推送规则以 RULES.md 为准；GitHub连接本身不会创建定时任务。

## 六段式固定模板
1. 本课要理解什么
2. 核心知识
3. 工业场景讲解
4. 能力与局限
5. 要点总结
6. 下一课

新课程使用上述标题；为兼容现有构建器，底层六个type仍保留原顺序，历史课程不批量重写。

## 课程覆盖范围
工业AI、自动化、控制与安全，并递进加入机器人触觉、工业与机器人数据、物理AI（Physical AI）。涵盖多模态感知、数据质量与评测、物理交互和仿真到现实迁移；按当期主题融入六段式，不要求每期涵盖全部方向。具体教学、证据与安全边界见 [RULES.md](RULES.md)。

## 新增课程与自动目录
将课程写入 content/lessons/YYYY-MM-DD.json；参考现有课程字段。
日期必须真实、文件名一致，每日一份主课程；同日修订更新原文件。
sections 的 type 必须依次为 research, case, knowledge, application, practice, conclusion。
每节 blocks 支持 heading/text/items/code/sources/answer；纯文本自动转义，来源仅允许 HTTPS。
level 固定“基础到应用”，duration 固定“阅读 10 分钟 · 实践 20–30 分钟”。
每日新增文件不需要手工编辑目录。构建扫描全部课程，生成首页、年份、月份与日期页面。

## 验证与发布
node scripts/build.mjs
node scripts/verify.mjs
node scripts/test.mjs
node scripts/stage.mjs

将内容提交并推送 main，GitHub Actions 自动构建、测试并部署 Pages。
Settings → Pages 的 Build and deployment 选择 GitHub Actions。
部署成功后核验公开首页、日期页面和目录交互，再分享链接。
课程定时推送为每周二、四、六上午10:00（已确认本地UTC−4）；网站也支持其他日期新增的课程，并不自动产生每日课程。
测试在临时目录模拟跨年、跨月课程，不将虚构课程发布。

## 数据与公开范围
仅提交可公开的原创教学内容及已核验来源。不提交聊天记录、个人标识、密钥或企业内部材料。
Pages 产物白名单仅为 HTML/CSS。无第三方脚本、追踪器或前端依赖。
复用同作者 daily-english-b2-c1 的静态归档引擎，工业课程独立维护。
