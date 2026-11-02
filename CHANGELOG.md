# CHANGELOG

所有显著变更都将记录在此文件中。

格式基于 [Keep a Changelog](https://keepachangelog.com/zh-CN/1.0.0/)。

版本遵循语义化版本规范：0.0.x（探索期）→ 0.x.y（验证期）→ x.y.z（正式期）

---

## [Unreleased]

### 删除

- `meta/` 整节（归位案例九篇）随 qtfounder `meta` 子命令淘汰而下线；已确认的标准属性与唯一确认公理已迁入元工程案例集（quanttide-gallery-of-meta-engineering `metaphysics/category/properties.md`），未确认内容留痕在本仓 git 历史；站点目录与首页清单同步

### 新增

- `media/rednote.md`：小红书与抖音双平台发布——Playwright 复制 Firefox profile 继承登录态，封面叠字、草稿箱恢复与五个踩坑点，附验收标准；`media/` 目录首篇
- `media/douyin.md`：抖音图文发布——与小红书的七项差异对照表，验证弹窗的人机交接流程，附验收标准

- `product/from-qtfounder-to-qtcloud.md`：qtfounder 给 qtcloud 探路——两仓并列、成果单向分岔，附三类不稳定、毕业标准与落位三问；新增 `product/` 目录（产品域）

- `human/training/product-operations.md`：产品运营培养方案——从用户体验观察入手，用 Issue 与 PR 记录成长路径；新增 `human/` 目录（人力资源域）
- `human/course-hiring-assessment.md`：把课程实践改造成招聘考核——任务与评分标准同源，门槛分设
- `human/screening-at-scale.md`：招聘筛选按申请量重设计——笔试退出，考核转入真实任务
- `human/crowdsourced-tasks.md`：众包任务连接需求、训练与选拔——真实需求拆成最小任务
- `human/promotion-stages.md`：晋升路径拆成可观察阶段——职级进度与候补过渡层
- `human/business-capability.md`：商务能力岗位化——岗位标准化后按获客与维护拆分
- `org/empowerment.md`：逐步授权——先定底线，随可靠行为让权，决议约束双方
- `org/points-ledger.md`：积分制发展成组织记录——互助行为用可核对记录支持
- `org/stage-leadership.md`：领导权随工作阶段流动——代表大会弱领导
- `org/resource-rules.md`：资源支持与组织规则共同演进——讲清价值与成本，走制度提案
- `work/continuous-process.md`：跨系统人工衔接转连续流程——先定义连续旅程再分段迁移
- `agent/intent-formalization.md`：先形式化意图再让 AI 和程序执行——规则与异常先行
- `agent/verifiable-records.md`：可核对记录支撑 AI 流程和交接——状态变更留记录、高影响步骤加校验
- `domain/human-vs-org.md`：域界线——人力资源与组织管理，以归到哪分界，手段不参与判断
- `asset/catalog.md`：资产清单——二十种资产的名字、路径、角色与布局
- `asset/relation.md`：资产关系——context、18 类长期记忆与 archive 的三种结构与搬迁关系
- `asset/maintain.md`：资产维护——三步流程与通过条件
- `org/right.md`：职权——代表大会弱领导，项目里随阶段流动

### 变更

- 移除 `meta/domain.md`；`index.md`、`meta/index.md`、`README.md`、`myst.yml` 目录与引用同步
- `asset/maintain.md`：不再镜像契约的九条规则，改为按 context → 长期记忆 → archive 的维护流程重写

### 变更

- `meta/model.md` 改为 `meta/model/index.md`；契约、规则、标准三页从规格降到 `meta/model/` 当标准模型

### 变更

- `meta/property.md`：十九条各带确认或怀疑，确认九条（id、name、label、title、path、status、description、category、type）；新增 `title`
- `meta/property.md`：六组统一叫「…属性」，`status` 单独归状态属性，`path` 归位置属性
- `meta/property.md`：「归属」拆成分类与位置状态；分类分 `category`（用户自定义）与 `type`（系统定义），`family` 作为格的类型字段归在 `type` 下
- `meta/property.md`：`statement`、`summary`、`boundary` 合并为 `description`
- `meta/property.md`：去掉 `key`，标识只用 `name`，中文称呼归 `label`
- `meta/axioms.md`：开头说明确认的排在前面
- `meta/index.md`：重写为四篇标准的入口——定位、目录、四样怎么合起来、为什么分四篇
- `meta/index.md`：评审引公理改为「写名字」，与公理的 `name` 字段一致
- `meta/axioms.md`：标记写进三级标题——`template-scope（确认）`，其余八条`（怀疑）`；每条前面的「状态」行省掉
- `meta/axioms.md`：`template-scope` 的前提改为「有固定结构才有模板」——日志有日期模板是因为输入格式固定，不是因为它在 `docs/` 下
- `media/` 目录更名为 `create/`：`media/food.md` → `create/food.md`（纯路径迁移，内容不变）；`index.md`、`README.md`、`myst.yml` 引用同步
- `devops/`：六篇按八阶段归档的清单迁出至 `quanttide-devops` 的案例集（`quanttide-gallery-of-devops` 的 `docs/gallery`），按阶段目录与主题文件重排，来源侧不留副本
- `work/agent/` 四篇移至顶层 `agent/`：智能体协作独立成域，不再归属 work；`myst.yml` 目录同步
- `work/export-icloud-photo.md`：按《work 语法》规格改写——散文管命令与取舍，块管步骤、判据、偏差与边界；收尾校验与常见偏差合并进块

### 新增

- `meta/domain.md`：标准领域——六个领域仓与各自的线索，均先标怀疑
- `meta/model.md`：标准模型——反复出现的五样形状（契约、单元、结论、命令、技能），每样给出定义、约束与出现处，均先标怀疑
- `meta/relation.md`：标准关系——反复出现的六种连接（包含、引用、派生、迁移、分组、定域），每样给出定义、约束与出现处，均先标怀疑
- `meta/property.md`：标准属性——id 用 uuid，name 做机器可读标识；归属、内容与关系字段各一条定义，按用途分组

- `meta/index.md`、`meta/axioms.md`：归位——先定域再定格四条顺序、落位卡点哪几条，以及评审里怎么引 id；公理清单单独成篇：按 `docs`、`meta`、`asset` 三组命令分节，以公理为单位，每条给前提与代价，判例附在对应公理下。前提与规则分开写，正本在 `qtfounder` 的归位契约里

- `code/`、`agent/`：踩坑清单留在产物与智能体两侧，自 `data/profile/pi/pitfalls.md` 迁入——代码三篇 16 条，协作纪律与 pi 运行时 16 条
- `language/context.md`：语境错配——财务与计算机术语搬出本领域的词表、替代写法与判断界线，自《汉语语用工程章程》第二章降级移入
- `work/agent/index.md`：智能体协作总览——适用范围、分工、操作、要点与已知限制，自手册迁入，来源侧不留副本
- `work/agent/desktop-workflow.md`：电脑端工作流——入口按职责分工，Zed 深度编辑、Pi TUI/Web 项目交互、Hermes desktop 跨多仓整理，OpenCode 与 dsh 为补充，自手册迁入
- `work/agent/mobile-workflow.md`：移动端工作流——手机经 Hermes 连电脑派单，电脑执行并推送 GitHub，手机用 Working Copy 查收、交官网 App 评审解读的闭环，自手册迁入
- `work/agent/hermes-workflow.md`：后台实现派单——对象/任务/交付/合格线四项要素、七步操作、派单模板与派单前检查，手机与电脑同一模板，自手册迁入
- `work/export-icloud-photo.md`：从 iCloud 相册导出照片与视频的工作流（认证前置、目录约定、照片/视频两条同步分支、HEIC→JPG 与 MOV→MP4 转码、Live Photo 归位、收尾校验与常见偏差），自手册的素材两篇合并迁入，来源侧不留副本；工作域在本仓重开
- 初始化案例集仓库：`README.md`（定位与同域分工）、`index.md`（入口，待补充）、`myst.yml`
- 新增 `media/` 目录：美食图文（`media/food.md`）

### 变更

- `media/food.md`：补全素材过程（同步、转码）与正文，店名与地址脱敏
- `media/food.md`：按探店方案修正选题定位，补入选图排序、封面、标题、文案、标签与待补清单
- `media/food.md`：补入滁州吾悦广场地址、人均与套餐价格、排队与停车信息
- `media/food.md`：画面无人出镜，按正常吃饭的口吻写，不标注合作角色
- `media/food.md`：补充店内多为 2–4 人、三四个人五六个菜的体验建议
- `media/food.md`：补全六道菜口感与茶饮温度，移除待补清单
- `media/food.md`：标题与说明改为图文，同一篇图文发在小红书和抖音
- `media/food.md`：补充平台标签上限与抖音只写后 4 个标签的策略
- `media/food.md`：补充 icloudpd 与 WorkBuddy 的工具说明，加工下的文案流程单独成节
- `media/douyin/food.md`：删除；平台拆分取消，案例合并到 `media/food.md`
- `work/rename.md`、`work/index.md`：迁出至 `quanttide-gallery-of-github-platform` 的 `second-brain/rename-files.md`，工作域在本仓清空

### 移除

- `work/founder-to-domain.md`：迁出至 GitHub 平台案例集 `second-brain/default-to-domain.md`，来源侧不留副本
- `work/background-implementation-delegation.md`：迁出至手册仓的 `work/`，来源侧不留副本
