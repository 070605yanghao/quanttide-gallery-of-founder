# 小红书与抖音双平台发布

用 Playwright 操作 Firefox，把探店图文按档案发布到小红书和抖音。上游是 [iCloud 照片导出](../work/export-icloud-photo.md) 与 [美食推荐图文](../create/food.md) 两条 work 的产出：转码落盘的 9 张图和写好的档案。

适用于有固定发布流程、内容已成档案、需要重复执行的平台发布场景；一次性随手发不值得走这条流程。

⚠️ 该方案（浏览器自动化发布）可能被平台判定为疑似 AI 操作，触发警告或风控；发布前评估账号风险，重要账号建议人工发布。

本篇分两半：**准备**给人做（一次性），**发布步骤**给执行器读。

## 准备（人做，一次性）

浏览器登录态不能直接给 Playwright 用，做法是复制系统 Firefox 的 profile 给持久化上下文，互不干扰：

```bash
# 装 Playwright 与其 Firefox
uv tool install playwright
playwright install firefox

# 复制正在使用的 profile（snap Firefox 路径）
mkdir -p /tmp/pw-profile
cp -r ~/snap/firefox/common/.mozilla/firefox/<profile> /tmp/pw-profile/ff
```

之后每次用 `launch_persistent_context("/tmp/pw-profile/ff")` 启动，小红书与抖音的登录态都在。系统 Firefox 与 Playwright Firefox 同时运行互不影响；`/tmp` 重启会清，丢了重新复制即可。

## 发布步骤

1. 封面叠字：用 Pillow 在封面图上叠三层文字——顶部品牌名、中部主标、底部副标，米黄字加深色描边；主标字号按最长一行试算，超宽会裁出画外。
2. 小红书：`creator.xiaohongshu.com/publish/publish` → 切「上传图文」→ 传图 → 填标题正文 → 正文末尾逐个 `#话题` 并点选下拉项 → 点底部「发布」。
3. 抖音：`creator.douyin.com/creator-micro/content/upload` → 切「发布图文」→ 传图 → 填标题描述话题 → 点「发布」→ 过短信验证。
4. 发布后以 URL 带 `published=true` 为成功凭证；小红书也可去笔记管理页复核。

## 踩过的坑

- **表单不渲染**：小红书发布页没有图片时标题、正文、发布按钮都不存在，必须先完成传图；抖音同理。探查 DOM 要在传图之后。
- **上传入口**：小红书要点「上传图文」tab（默认停在「上传视频」），tab 点击会被父级拦截，用 `evaluate("el => el.click()")` 绕过；抖音页面上有多个 `input[type=file]`，图片的是 `accept` 含 `image/` 且带 `multiple` 的那个。
- **会话不跨导航**：重新 goto 发布页后表单清空，内容在草稿箱（小红书），可从「草稿箱 → 图文笔记 → 编辑」恢复；稳妥做法是填表与点发布放同一次会话。
- **发布按钮**：小红书底部「发布」不是 button 元素，文本匹配会先命中左侧「发布笔记」菜单（点了会跳回空白页），按坐标点底部那颗；抖音是标准 `button`，取最后一个。
- **人机验证**：抖音首次发布弹短信验证码，只能人来收码，执行器停在弹窗处等输入。
- **平台风控**：自动化操作可能被平台判定为疑似 AI，触发警告甚至限流；被警告时停止自动化，转人工发布，不要反复重试。

## 验收标准

```yaml work
work: rednote-publish
标题: 小红书与抖音双平台发布
版本: 1

输入:
  档案: { 必填: true }        # data/profile/create/<店名>.md，含标题/文案/标签/图片清单
  平台: { 默认: [小红书, 抖音] }

前置:
  - 档案存在且图片清单九张齐备
  - Playwright Firefox profile 已复制且两平台登录态有效

步骤:
  - 封面叠字: 按档案「图片」节的封面方案生成叠字图
  - 小红书发布: 十个话题全部成蓝色可点状态后点发布
  - 抖音发布: 按档案「平台限制」只带后四个话题，短信验证由人完成
  - 凭证记录: 记录两平台发布成功 URL 或笔记链接

验收:
  - 小红书 URL 含 published=true 或笔记管理页可见该笔记
  - 抖音内容管理页可见该作品
  - 两平台标题、话题数符合档案「平台限制」
```

## 不做

- 选题、选图、文案与标签（在[美食推荐图文](../create/food.md)）
- 素材同步与转码（在 [导出 iCloud 照片](../work/export-icloud-photo.md)）
- 数据回流与效果复盘
