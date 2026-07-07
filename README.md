# wisdom-roundtable

智慧圆桌：11 位思想家的认知框架并行独立分析你的决策。

## 这是什么 / 解决什么问题

当你在做决策、评估方案或想听不同视角时，单个 Agent 很容易沿着一个思路一路滑下去。这个 skill 会从 11 位公众人物的认知框架中选择最相关的 2-4 位，让每个视角独立分析，再汇总共识、分歧和行动建议。核心不是角色扮演，而是把公开言论和实践中可复用的心智模型抽出来，用于辅助思考。

本 skill 中的 persona 是对相关公众人物公开言论、作品与实践中认知框架的模拟提炼，与本人无关联，未获本人授权，不代表本人观点。输出应表述为「某某认知框架视角」，不得假装本人发言、不得用于冒充本人。各 persona 文件中的「盲区/矛盾」类段落是公开报道与社区批评的概括，用于提示该认知框架的局限，未逐条核实、不构成事实断言；引用其中具体事实前请自行核验。

## 核心功能/亮点

- 自动根据问题推荐 2-4 个最相关的认知框架
- 支持并行子代理时，多个视角真正独立分析，互相不可见
- 不支持并行子代理时，降级为串行独立分析并明确提示锚定风险
- 先给圆桌总结，再展开各视角详细分析
- 对分歧最大的两种视角可自动生成交锋环节
- persona 文件自带心智模型、决策启发式、表达风格和盲区说明

## 安装

Claude Code：

```bash
git clone https://github.com/ruodou233/wisdom-roundtable.git ~/.claude/skills/wisdom-roundtable
```

Codex：

```bash
git clone https://github.com/ruodou233/wisdom-roundtable.git ~/.agents/skills/wisdom-roundtable
```

其他支持 SKILL.md 的平台：放入其 skills 目录即可。

## 使用示例

- 「我该不该辞职做自己的 AI 产品？圆桌看看」
  - 预期行为：推荐芒格、Naval、Karpathy、Paul Graham 等视角，分别分析风险、杠杆、AI 工程现实和创业路径。
- 「这个短视频选题怎么优化？让 MrBeast 和乔布斯视角看看」
  - 预期行为：按指定人选分析点击、留存、传达和产品感。
- 「我们公司未来三年的战略方向，给我多几个视角」
  - 预期行为：选择商业、产品、组织、风险等互补视角，先汇总共识与分歧，再展开各方判断。

## 首次使用：环境自适应

本 skill 无需 local-config。运行前由你的 Agent 只读检测所在平台是否支持并行子代理：

- 支持并行子代理：按 SKILL.md 原流程并行运行，每个 persona 独立分析。
- 不支持并行子代理：降级为串行独立分析，并向你声明「串行存在锚定风险，各视角独立性弱于并行」。
- Claude Code 示例中的 `subagent_type: "claude"` 是平台写法；其他平台使用等价的并行子代理或独立分析机制。

## Changelog

| 时间 | 变更 |
|---|---|
| 2026-07 | 首次开源发布 |

## 反馈与作者

这个 skill 我长期维护。如果你有修改方案、发现问题、或者改出了更好的版本，欢迎通过以下任一渠道找到我：

- GitHub：本仓库提 issue 或 PR
- 小红书：错误乱码
- 微信公众号：能工智人错误乱码
- B站：若逗道人

## 相关 Skill 推荐

<!-- 本表由维护脚本生成，勿手工编辑 -->
- [domain-explorer](https://github.com/ruodou233/domain-explorer)：速通新领域：四线并行调研，产出交互式知识地图
- [improve-product-plan](https://github.com/ruodou233/improve-product-plan)：把模糊的产品想法梳理成可开发、可验收的 SPEC.md
- [de-ai-taste](https://github.com/ruodou233/de-ai-taste)：中文去 AI 味：逐条检测 AI 生成痕迹并给修改建议

完整目录见 [GitHub 主页](https://github.com/ruodou233)。
