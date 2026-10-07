# 工业 AI 研究周报与学习课程
公开网站：https://daniel-netsecu.github.io/industrial-ai-study/

## 六段式固定模板
1. 研究动态（日期、来源、证据边界）
2. 案例深读（问题、数据、方法、效果与局限）
3. 自动化知识（2—3个递进概念）
4. 应用方案（场景、数据、系统、人机权限）
5. 动手练习（20—30分钟、模拟数据、步骤、参考答案）
6. 结论与下期（验收、待验证假设、下一课）

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
周报定时任务保留每周三；网站也支持其他日期新增的课程，并不自动产生每日课程。
测试在临时目录模拟跨年、跨月课程，不将虚构课程发布。

## 数据与公开范围
仅提交可公开的原创教学内容及已核验来源。不提交聊天记录、个人标识、密钥或企业内部材料。
Pages 产物白名单仅为 HTML/CSS。无第三方脚本、追踪器或前端依赖。
复用同作者 daily-english-b2-c1 的静态归档引擎，工业课程独立维护。
