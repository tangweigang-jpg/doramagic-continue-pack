# AI Context Pack

## Pack Identity

- Upstream: https://github.com/continuedev/continue
- Pack type: AI Coding Workflow Governance Pack
- Doramagic canonical: https://doramagic.ai/projects/continue/
- Relationship: independent pack; not affiliated or endorsed unless explicitly stated.

## Operating Rules

- Evidence first.
- No official endorsement claim.
- Run evals before claiming success.
- Use pitfall and risk files for recovery.

## Host Files

- `../AGENTS.md`
- `../CLAUDE.md`

## Doramagic Source Extract

# continue - Doramagic AI Context Pack

> 定位：安装前体验与判断资产。它帮助宿主 AI 有一个好的开始，但不代表已经安装、执行或验证目标项目。

## 充分原则

- **充分原则，不是压缩原则**：AI Context Pack 应该充分到让宿主 AI 在开工前理解项目价值、能力边界、使用入口、风险和证据来源；它可以分层组织，但不以最短摘要为目标。
- **压缩策略**：只压缩噪声和重复内容，不压缩会影响判断和开工质量的上下文。

## 给宿主 AI 的使用方式

你正在读取 Doramagic 为 continue 编译的 AI Context Pack。请把它当作开工前上下文：帮助用户理解适合谁、能做什么、如何开始、哪些必须安装后验证、风险在哪里。不要声称你已经安装、运行或执行了目标项目。

## Claim 消费规则

- **事实来源**：Repo Evidence + Claim/Evidence Graph；Human Wiki 只提供显著性、术语和叙事结构。
- **事实最低状态**：`supported`
- `supported`：可以作为项目事实使用，但回答中必须引用 claim_id 和证据路径。
- `weak`：只能作为低置信度线索，必须要求用户继续核实。
- `inferred`：只能用于风险提示或待确认问题，不能包装成项目事实。
- `unverified`：不得作为事实使用，应明确说证据不足。
- `contradicted`：必须展示冲突来源，不得替用户强行选择一个版本。

## 它最适合谁

- **希望把专业流程带进宿主 AI 的用户**：仓库包含 Skill 文档。 证据：`.claude/skills/docs-style/SKILL.md`, `skills/cn-check/SKILL.md` Claim：`clm_0003` supported 0.86

## 它能做什么

- **AI Skill / Agent 指令资产库**（可做安装前预览）：项目包含可被宿主 AI 读取的 Skill 或 Agent 指令文件，可用于把专业流程带入 Claude、Codex、Cursor 等宿主。 证据：`.claude/skills/docs-style/SKILL.md`, `skills/cn-check/SKILL.md` Claim：`clm_0001` supported 0.86
- **命令行启动或安装流程**（需要安装后验证）：项目文档中存在可执行命令，真实使用需要在本地或宿主环境中运行这些命令。 证据：`README.md`, `packages/continue-sdk/python/api/README.md`, `packages/continue-sdk/typescript/README.md`, `packages/continue-sdk/typescript/api/README.md` Claim：`clm_0002` supported 0.86

## 怎么开始

- `curl -fsSL https://raw.githubusercontent.com/continuedev/continue/main/extensions/cli/scripts/install.sh | bash` 证据：`README.md` Claim：`clm_0004` supported 0.86
- `npm i -g @continuedev/cli` 证据：`README.md` Claim：`clm_0005` supported 0.86
- `pip install git+https://github.com/GIT_USER_ID/GIT_REPO_ID.git` 证据：`packages/continue-sdk/python/api/README.md` Claim：`clm_0006` supported 0.86
- `npm install @continuedev/hub-api@0.0.1 --save` 证据：`packages/continue-sdk/typescript/api/README.md` Claim：`clm_0007` supported 0.86
- `npm install PATH_TO_GENERATED_PACKAGE --save` 证据：`packages/continue-sdk/typescript/api/README.md` Claim：`clm_0008` supported 0.86
- `npm install @continuedev/sdk` 证据：`packages/continue-sdk/typescript/README.md` Claim：`clm_0009` supported 0.86

## 继续前判断卡

- **当前建议**：需要管理员/安全审批
- **为什么**：继续前可能涉及密钥、账号、外部服务或敏感上下文，建议先经过管理员或安全审批。

### 30 秒判断

- **现在怎么做**：需要管理员/安全审批
- **最小安全下一步**：先跑 Prompt Preview；若涉及凭证或企业环境，先审批再试装
- **先别相信**：真实输出质量不能在安装前相信。
- **继续会触碰**：命令执行、宿主 AI 配置、本地环境或项目文件

### 现在可以相信

- **适合人群线索：希望把专业流程带进宿主 AI 的用户**（supported）：有 supported claim 或项目证据支撑，但仍不等于真实安装效果。 证据：`.claude/skills/docs-style/SKILL.md`, `skills/cn-check/SKILL.md` Claim：`clm_0003` supported 0.86
- **能力存在：AI Skill / Agent 指令资产库**（supported）：可以相信项目包含这类能力线索；是否适合你的具体任务仍要试用或安装后验证。 证据：`.claude/skills/docs-style/SKILL.md`, `skills/cn-check/SKILL.md` Claim：`clm_0001` supported 0.86
- **能力存在：命令行启动或安装流程**（supported）：可以相信项目包含这类能力线索；是否适合你的具体任务仍要试用或安装后验证。 证据：`README.md`, `packages/continue-sdk/python/api/README.md`, `packages/continue-sdk/typescript/README.md`, `packages/continue-sdk/typescript/api/README.md` Claim：`clm_0002` supported 0.86
- **存在 Quick Start / 安装命令线索**（supported）：可以相信项目文档出现过启动或安装入口；不要因此直接在主力环境运行。 证据：`README.md` Claim：`clm_0004` supported 0.86

### 现在还不能相信

- **真实输出质量不能在安装前相信。**（unverified）：Prompt Preview 只能展示引导方式，不能证明真实项目中的结果质量。
- **宿主 AI 版本兼容性不能在安装前相信。**（unverified）：Claude、Cursor、Codex、Gemini 等宿主加载规则和版本差异必须在真实环境验证。
- **不会污染现有宿主 AI 行为，不能直接相信。**（inferred）：Skill、plugin、AGENTS/CLAUDE/GEMINI 指令可能改变宿主 AI 的默认行为。 证据：`.claude/skills/docs-style/SKILL.md`, `skills/cn-check/SKILL.md`
- **可安全回滚不能默认相信。**（unverified）：除非项目明确提供卸载和恢复说明，否则必须先在隔离环境验证。
- **真实安装后是否与用户当前宿主 AI 版本兼容？**（unverified）：兼容性只能通过实际宿主环境验证。
- **项目输出质量是否满足用户具体任务？**（unverified）：安装前预览只能展示流程和边界，不能替代真实评测。
- **安装命令是否需要网络、权限或全局写入？**（unverified）：这影响企业环境和个人环境的安装风险。 证据：`README.md`

### 继续会触碰什么

- **命令执行**：包管理器、网络下载、本地插件目录、项目配置或用户主目录。 原因：运行第一条命令就可能产生环境改动；必须先判断是否值得跑。 证据：`README.md`, `packages/continue-sdk/python/api/README.md`, `packages/continue-sdk/typescript/README.md`, `packages/continue-sdk/typescript/api/README.md`
- **宿主 AI 配置**：Claude/Codex/Cursor/Gemini/OpenCode 等宿主的 plugin、Skill 或规则加载配置。 原因：宿主配置会改变 AI 后续工作方式，可能和用户已有规则冲突。 证据：`.claude/skills/docs-style/SKILL.md`, `skills/cn-check/SKILL.md`
- **本地环境或项目文件**：安装结果、插件缓存、项目配置或本地依赖目录。 原因：安装前无法证明写入范围和回滚方式，需要隔离验证。 证据：`README.md`, `packages/continue-sdk/python/api/README.md`, `packages/continue-sdk/typescript/README.md`, `packages/continue-sdk/typescript/api/README.md`
- **环境变量 / API Key**：项目入口文档明确出现 API key、token、secret 或账号凭证配置。 原因：如果真实安装需要凭证，应先使用测试凭证并经过权限/合规判断。 证据：`packages/continue-sdk/python/api/README.md`, `packages/continue-sdk/python/api/docs/DefaultApi.md`
- **宿主 AI 上下文**：AI Context Pack、Prompt Preview、Skill 路由、风险规则和项目事实。 原因：导入上下文会影响宿主 AI 后续判断，必须避免把未验证项包装成事实。

### 最小安全下一步

- **先跑 Prompt Preview**：用安装前交互式试用判断工作方式是否匹配，不需要授权或改环境。（适用：任何项目都适用，尤其是输出质量未知时。）
- **只在隔离目录或测试账号试装**：避免安装命令污染主力宿主 AI、真实项目或用户主目录。（适用：存在命令执行、插件配置或本地写入线索时。）
- **先备份宿主 AI 配置**：Skill、plugin、规则文件可能改变 Claude/Cursor/Codex 的默认行为。（适用：存在插件 manifest、Skill 或宿主规则入口时。）
- **不要使用真实生产凭证**：环境变量/API key 一旦进入宿主或工具链，可能产生账号和合规风险。（适用：出现 API、TOKEN、KEY、SECRET 等环境线索时。）
- **安装后只验证一个最小任务**：先验证加载、兼容、输出质量和回滚，再决定是否深用。（适用：准备从试用进入真实工作流时。）

### 退出方式

- **保留安装前状态**：记录原始宿主配置和项目状态，后续才能判断是否可恢复。
- **准备移除宿主 plugin / Skill / 规则入口**：如果试装后行为异常，可以把宿主 AI 恢复到试装前状态。
- **记录安装命令和写入路径**：没有明确卸载说明时，至少要知道哪些目录或配置需要手动清理。
- **准备撤销测试 API key 或 token**：测试凭证泄露或误用时，可以快速止损。
- **如果没有回滚路径，不进入主力环境**：不可回滚是继续前阻断项，不应靠信任或运气继续。

## 哪些只能预览

- 解释项目适合谁和能做什么
- 基于项目文档演示典型对话流程
- 帮助用户判断是否值得安装或继续研究

## 哪些必须安装后验证

- 真实安装 Skill、插件或 CLI
- 执行脚本、修改本地文件或访问外部服务
- 验证真实输出质量、性能和兼容性

## 边界与风险判断卡

- **把安装前预览误认为真实运行**：用户可能高估项目已经完成的配置、权限和兼容性验证。 处理方式：明确区分 prompt_preview_can_do 与 runtime_required。 Claim：`clm_0010` inferred 0.45
- **命令执行会修改本地环境**：安装命令可能写入用户主目录、宿主插件目录或项目配置。 处理方式：先在隔离环境或测试账号中运行。 证据：`README.md`, `packages/continue-sdk/python/api/README.md`, `packages/continue-sdk/typescript/README.md`, `packages/continue-sdk/typescript/api/README.md` Claim：`clm_0011` supported 0.86
- **待确认**：真实安装后是否与用户当前宿主 AI 版本兼容？。原因：兼容性只能通过实际宿主环境验证。
- **待确认**：项目输出质量是否满足用户具体任务？。原因：安装前预览只能展示流程和边界，不能替代真实评测。
- **待确认**：安装命令是否需要网络、权限或全局写入？。原因：这影响企业环境和个人环境的安装风险。

## 开工前工作上下文

### 加载顺序

- 先读取 how_to_use.host_ai_instruction，建立安装前判断资产的边界。
- 读取 claim_graph_summary，确认事实来自 Claim/Evidence Graph，而不是 Human Wiki 叙事。
- 再读取 intended_users、capabilities 和 quick_start_candidates，判断用户是否匹配。
- 需要执行具体任务时，优先查 role_skill_index，再查 evidence_index。
- 遇到真实安装、文件修改、网络访问、性能或兼容性问题时，转入 risk_card 和 boundaries.runtime_required。

### 任务路由

- **AI Skill / Agent 指令资产库**：先基于 role_skill_index / evidence_index 帮用户挑选可用角色、Skill 或工作流。 边界：可做安装前 Prompt 体验。 证据：`.claude/skills/docs-style/SKILL.md`, `skills/cn-check/SKILL.md` Claim：`clm_0001` supported 0.86
- **命令行启动或安装流程**：先说明这是安装后验证能力，再给出安装前检查清单。 边界：必须真实安装或运行后验证。 证据：`README.md`, `packages/continue-sdk/python/api/README.md`, `packages/continue-sdk/typescript/README.md`, `packages/continue-sdk/typescript/api/README.md` Claim：`clm_0002` supported 0.86

### 上下文规模

- 文件总数：2801
- 重要文件覆盖：40/2801
- 证据索引条目：80
- 角色 / Skill 条目：2

### 证据不足时的处理

- **missing_evidence**：说明证据不足，要求用户提供目标文件、README 段落或安装后验证记录；不要补全事实。
- **out_of_scope_request**：说明该任务超出当前 AI Context Pack 证据范围，并建议用户先查看 Human Manual 或真实安装后验证。
- **runtime_request**：给出安装前检查清单和命令来源，但不要替用户执行命令或声称已执行。
- **source_conflict**：同时展示冲突来源，标记为待核实，不要强行选择一个版本。

## Prompt Recipes

### 适配判断

- 目标：判断这个项目是否适合用户当前任务。
- 预期输出：适配结论、关键理由、证据引用、安装前可预览内容、必须安装后验证内容、下一步建议。

```text
请基于 continue 的 AI Context Pack，先问我 3 个必要问题，然后判断它是否适合我的任务。回答必须包含：适合谁、能做什么、不能做什么、是否值得安装、证据来自哪里。所有项目事实必须引用 evidence_refs、source_paths 或 claim_id。
```

### 安装前体验

- 目标：让用户在安装前感受核心工作流，同时避免把预览包装成真实能力或营销承诺。
- 预期输出：一段带边界标签的体验剧本、安装后验证清单和谨慎建议；不含真实运行承诺或强营销表述。

```text
请把 continue 当作安装前体验资产，而不是已安装工具或真实运行环境。

请严格输出四段：
1. 先问我 3 个必要问题。
2. 给出一段“体验剧本”：用 [安装前可预览]、[必须安装后验证]、[证据不足] 三种标签展示它可能如何引导工作流。
3. 给出安装后验证清单：列出哪些能力只有真实安装、真实宿主加载、真实项目运行后才能确认。
4. 给出谨慎建议：只能说“值得继续研究/试装”“先补充信息后再判断”或“不建议继续”，不得替项目背书。

硬性边界：
- 不要声称已经安装、运行、执行测试、修改文件或产生真实结果。
- 不要写“自动适配”“确保通过”“完美适配”“强烈建议安装”等承诺性表达。
- 如果描述安装后的工作方式，必须使用“如果安装成功且宿主正确加载 Skill，它可能会……”这种条件句。
- 体验剧本只能写成“示例台词/假设流程”：使用“可能会询问/可能会建议/可能会展示”，不要写“已写入、已生成、已通过、正在运行、正在生成”。
- Prompt Preview 不负责给安装命令；如用户准备试装，只能提示先阅读 Quick Start 和 Risk Card，并在隔离环境验证。
- 所有项目事实必须来自 supported claim、evidence_refs 或 source_paths；inferred/unverified 只能作风险或待确认项。

```

### 角色 / Skill 选择

- 目标：从项目里的角色或 Skill 中挑选最匹配的资产。
- 预期输出：候选角色或 Skill 列表，每项包含适用场景、证据路径、风险边界和是否需要安装后验证。

```text
请读取 role_skill_index，根据我的目标任务推荐 3-5 个最相关的角色或 Skill。每个推荐都要说明适用场景、可能输出、风险边界和 evidence_refs。
```

### 风险预检

- 目标：安装或引入前识别环境、权限、规则冲突和质量风险。
- 预期输出：环境、权限、依赖、许可、宿主冲突、质量风险和未知项的检查清单。

```text
请基于 risk_card、boundaries 和 quick_start_candidates，给我一份安装前风险预检清单。不要替我执行命令，只说明我应该检查什么、为什么检查、失败会有什么影响。
```

### 宿主 AI 开工指令

- 目标：把项目上下文转成一次对话开始前的宿主 AI 指令。
- 预期输出：一段边界明确、证据引用明确、适合复制给宿主 AI 的开工前指令。

```text
请基于 continue 的 AI Context Pack，生成一段我可以粘贴给宿主 AI 的开工前指令。这段指令必须遵守 not_runtime=true，不能声称项目已经安装、运行或产生真实结果。
```


## 角色 / Skill 索引

- 共索引 2 个角色 / Skill / 项目文档条目。

- **docs-style**（skill）：Style guidelines for writing and updating documentation. Use when writing new docs, updating existing docs, or reviewing docs for quality. 激活提示：当用户任务与“docs-style”描述的流程高度相关时，先用它做安装前体验，再决定是否安装。 证据：`.claude/skills/docs-style/SKILL.md`
- **cn-check**（skill）：Install and run the Continue CLI cn to execute AI agent checks on local code changes. Use when asked to "run checks", "lint with AI", "review my changes with cn", or set up Continue CI locally. 激活提示：当用户任务与“cn-check”描述的流程高度相关时，先用它做安装前体验，再决定是否安装。 证据：`skills/cn-check/SKILL.md`

## 证据索引

- 共索引 80 条证据。

- **Mintlify Starter Kit**（documentation）：Click on Use this template to copy the Mintlify starter kit. The starter kit contains examples including 证据：`docs/README.md`
- **Getting started**（documentation）：Source-controlled AI checks, enforceable in CI 证据：`README.md`
- **Continue PR Review Actions**（documentation）：GitHub Actions that provide automated code reviews for pull requests using Continue CLI. 证据：`actions/README.md`
- **Continue Core Binary**（documentation）：The purpose of this folder is to package Typescript code in a way that can be run from any IDE or platform. We first bundle with esbuild and then package into binaries with pkg . 证据：`binary/README.md`
- **Continue React App**（documentation）：The Continue React app is a notebook-like interface to the Continue server. It allows the user to submit arbitrary text input, then communicates with the server to takes steps, which are displayed as a sequence of editable cells. The React app should sit beside an IDE, as in the VS Code extension. 证据：`gui/README.md`
- **Readme**（documentation）：The sole purpose of this folder is to open it when debugging the extension. It is not used by the extension itself. You can add more files that can be useful when manually testing the extension. 证据：`manual-testing-sandbox/readme.md`
- **Indexing**（documentation）：Continue uses a tagging system along with content addressing to ensure that nothing needs to be indexed twice. When you change branches, Continue will only re-index the files that are newly modified and that we don't already have a copy of. This system can be used across many different "artifacts" just by implementing the CodebaseIndex class. 证据：`core/indexing/README.md`
- **Next Edit Prediction**（documentation）：How is it different from autocomplete? 证据：`core/nextEdit/README.md`
- **Vendored node modules**（documentation）：- transformers.js: to avoid the sharp dependency, which isn't used and has native dependencies 证据：`core/vendor/README.md`
- **Quick tour**（documentation）：State-of-the-art Machine Learning for the web. Run 🤗 Transformers directly in your browser, with no need for a server! 证据：`core/vendor/modules/@xenova/transformers/README.md`
- **AGENTS.md**（documentation）：This file provides guidance to AI coding agents when working with code in this repository. 证据：`extensions/cli/AGENTS.md`
- **Continue CLI**（documentation）：The Continue CLI cn is a customizable command line coding agent. 证据：`extensions/cli/README.md`
- **Tool Permissions System**（documentation）：The tool permissions system allows you to control which tools the AI can use and how it can use them. There are three permission levels: 证据：`extensions/cli/src/permissions/README.md`
- **TUI Testing Framework**（documentation）：This directory contains a comprehensive testing framework for the Continue CLI's Terminal User Interface TUI that supports running tests in both normal local and remote modes. 证据：`extensions/cli/src/ui/__tests__/README.md`
- **JetBrains Agent**（documentation）：Source-controlled AI checks, enforceable in CI https://docs.continue.dev 证据：`extensions/intellij/README.md`
- **VS Code Agent**（documentation）：Source-controlled AI checks, enforceable in CI https://docs.continue.dev 证据：`extensions/vscode/README.md`
- **E2E Tests**（documentation）：When running e2e tests for the first time 证据：`extensions/vscode/e2e/README.md`
- **Readme**（documentation）：all-MiniLM-L6-v2 is the sentence transformers model used with transformers.js to locally generate codebase embeddings. 证据：`extensions/vscode/models/README.md`
- **Usage Transformers.js**（documentation）：https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2 with ONNX weights to be compatible with Transformers.js. 证据：`extensions/vscode/models/all-MiniLM-L6-v2/README.md`
- **config.yaml specification**（documentation）：This specification is a work in progress and subject to change. 证据：`packages/config-yaml/src/README.md`
- **@continuedev/sdk**（documentation）：⚠️ EXPERIMENTAL: This package is in early development and subject to frequent breaking changes without notice. 证据：`packages/continue-sdk/README.md`
- **@continuedev/sdk**（documentation）：⚠️ EXPERIMENTAL: This package is in early development and subject to frequent breaking changes without notice. 证据：`packages/continue-sdk/python/README.md`
- **openapi-client**（documentation）：API for Continue IDE to fetch assistants and other related information. These endpoints are primarily used by the Continue IDE extensions for VS Code and JetBrains. 证据：`packages/continue-sdk/python/api/README.md`
- **@continuedev/sdk**（documentation）：⚠️ EXPERIMENTAL: This package is in early development and subject to frequent breaking changes without notice. 证据：`packages/continue-sdk/typescript/README.md`
- **@continuedev/hub-api@0.0.1**（documentation）：This generator creates TypeScript/JavaScript client that utilizes Fetch API https://fetch.spec.whatwg.org/ . The generated Node module can be used in the following environments: 证据：`packages/continue-sdk/typescript/api/README.md`
- **@continuedev/llm-info**（documentation）：A lightweight package providing information about various Large Language Models LLMs , including embedding, reranking, and other models. 证据：`packages/llm-info/README.md`
- **OpenAI Adapters**（documentation）：OpenAI adapters convert an OpenAI-compatible request to a request for another API and back. 证据：`packages/openai-adapters/README.md`
- **Codebase Indexing**（documentation）：This is a small Rust library for efficiently keeping a codebase index up to date. 证据：`sync/src/README.md`
- **Package**（package_manifest）：{ "name": "binary", "version": "1.0.0", "author": "Continue Dev, Inc", "description": "", "main": "out/index.js", "bin": "out/index.js", "pkg": { "scripts": "node modules/axios/ / " , "assets": "../core/node modules/sqlite3/ / ", "node modules/@lancedb/ / ", "out/tree-sitter.wasm", "out/tree-sitter-wasms/ " , "targets": "node18-darwin-arm64" , "outputPath": "bin" }, "scripts": { "test": "jest", "build": "node build.js", "rebuild": "node build.js --esbuild-only", "build:darwin-x64": "node build.js --os darwin-x64" }, "license": "Apache-2.0", "devDependencies": { "@biomejs/biome": "1.6.4", "@types/follow-redirects": "^1.14.4", "@types/jest": "^29.5.12", "@types/uuid": "^9.0.8", "@vercel/ncc":… 证据：`binary/package.json`
- **Package**（package_manifest）：{ "name": "@continuedev/core", "version": "1.1.0", "description": "The Continue Core contains functionality that can be shared across web, VS Code, or Node.js", "scripts": { "test": "cross-env NODE OPTIONS=--experimental-vm-modules jest", "vitest": "vitest run", "test:coverage": "cross-env NODE OPTIONS=--experimental-vm-modules jest --coverage && open ./coverage/lcov-report/index.html", "tsc:check": "tsc -p ./ --noEmit", "build": "tsc -p ./tsconfig.npm.json", "build:npm": "npm run build && npm run sentry:sourcemaps", "lint": "eslint . --ext ts", "lint:fix": "eslint . --ext ts --fix", "sentry:sourcemaps": "sentry-cli sourcemaps inject --org continue-xd --project continue ./dist && sentry-cli… 证据：`core/package.json`
- **Package**（package_manifest）：{ "name": "docs2", "version": "1.0.0", "description": "Click on Use this template to copy the Mintlify starter kit. The starter kit contains examples including", "main": "index.js", "scripts": { "dev": "mintlify dev", "build": "mintlify build", "test": "echo \"Error: no test specified\" && exit 1" }, "keywords": , "author": "", "license": "ISC", "type": "commonjs", "devDependencies": { "mintlify": "^4.2.454" }, "dependencies": { "@c15t/react": "^1.8.5", "axios": "^1.13.6", "tar-fs": "^3.1.2" }, "overrides": { "express": "^4.21.2", "qs": "^6.14.2", "tar": "^7.5.13", "js-yaml": "^4.1.1", "lodash": "^4.17.23", "zod": "^3.24.0", "axios": "^1.13.6", "@orpc/openapi": "^1.13.11", "kysely": "^0.28.… 证据：`docs/package.json`
- **Package**（package_manifest）：{ "name": "gui", "private": true, "type": "module", "author": "Continue Dev, Inc", "license": "Apache-2.0", "scripts": { "dev": "vite", "tsc:check": "tsc -p ./ --noEmit", "build": "tsc && vite build", "preview": "vite preview", "test": "vitest run", "test:coverage": "vitest run --coverage", "test:ui": "vitest --ui", "test:watch": "vitest", "lint": "eslint --ext ts" }, "dependencies": { "@continuedev/config-yaml": "file:../packages/config-yaml", "@continuedev/terminal-security": "file:../packages/terminal-security", "@headlessui/react": "^2.2.0", "@heroicons/react": "^2.0.18", "@modelcontextprotocol/ext-apps": "^1.0.1", "@panzoom/panzoom": "^4.6.0", "@reduxjs/toolkit": "^2.11.2", "@sentry/re… 证据：`gui/package.json`
- **Package**（package_manifest）：{ "name": "continue", "scripts": { "tsc:watch": "concurrently -n gui,vscode,core,binary -c cyan,magenta,yellow,green \"npm run tsc:watch:gui\" \"npm run tsc:watch:vscode\" \"npm run tsc:watch:core\" \"npm run tsc:watch:binary\"", "tsc:watch:gui": "tsc --project gui/tsconfig.json --watch --noEmit --pretty", "tsc:watch:vscode": "tsc --project extensions/vscode/tsconfig.json --watch --noEmit --pretty", "tsc:watch:core": "tsc --project core/tsconfig.json --watch --noEmit --pretty", "tsc:watch:binary": "tsc --project binary/tsconfig.json --watch --noEmit --pretty", "format": "prettier --write \" / .{js,jsx,ts,tsx,json,css,md}\" --ignore-path .gitignore --ignore-path .prettierignore", "format:che… 证据：`package.json`
- **Contributing to Continue**（documentation）：- Contributing to Continue contributing-to-continue - Table of Contents table-of-contents - ❤️ Ways to Contribute ️-ways-to-contribute - 👋 Continue Contribution Ideas -continue-contribution-ideas - 🐛 Report Bugs -report-bugs - ✨ Suggest Enhancements -suggest-enhancements - 📖 Updating / Improving Documentation -updating--improving-documentation - Running the Documentation Server Locally running-the-documentation-server-locally - Method 1: NPM Script method-1-npm-script - Method 2: VS Code Task method-2-vs-code-task - 🧑‍💻 Contributing Code -contributing-code - Environment Setup environment-setup - Pre-requisites pre-requisites - Fork the Continue Repository fork-the-continue-repository - VS C… 证据：`CONTRIBUTING.md`
- **Package**（package_manifest）：{ "name": "continue-binary", "version": "1.0.0", "description": "", "bin": "../../out/index.js", "pkg": { "scripts": "node modules/axios/ / " , "assets": "../../../core/node modules/sqlite3/ / ", "../../out/tree-sitter.wasm", "../../out/tree-sitter-wasms/ ", "../../tree-sitter/ / ", "../../out/llamaTokenizer.mjs", "../../out/llamaTokenizerWorkerPool.mjs", "../../out/tiktokenWorkerPool.mjs", "../../out/package.json" , "targets": "node18-macos-arm64" , "outputPath": "bin" }, "author": "", "license": "Apache-2.0" } 证据：`binary/pkgJson/darwin-arm64/package.json`
- **Package**（package_manifest）：{ "name": "continue-binary", "version": "1.0.0", "description": "", "bin": "../../out/index.js", "pkg": { "scripts": "node modules/axios/ / " , "assets": "../../../core/node modules/sqlite3/ / ", "../../out/tree-sitter.wasm", "../../out/tree-sitter-wasms/ ", "../../tree-sitter/ / ", "../../out/llamaTokenizer.mjs", "../../out/llamaTokenizerWorkerPool.mjs", "../../out/tiktokenWorkerPool.mjs", "../../out/package.json" , "targets": "node18-macos-x64" , "outputPath": "bin" }, "author": "", "license": "Apache-2.0" } 证据：`binary/pkgJson/darwin-x64/package.json`
- **Package**（package_manifest）：{ "name": "continue-binary", "version": "1.0.0", "description": "", "bin": "../../out/index.js", "pkg": { "scripts": "node modules/axios/ / " , "assets": "../../../core/node modules/sqlite3/ / ", "../../out/tree-sitter.wasm", "../../out/tree-sitter-wasms/ ", "../../tree-sitter/ / ", "../../out/llamaTokenizer.mjs", "../../out/llamaTokenizerWorkerPool.mjs", "../../out/tiktokenWorkerPool.mjs", "../../out/package.json" , "targets": "node18-linux-arm64" , "outputPath": "bin" }, "author": "", "license": "Apache-2.0" } 证据：`binary/pkgJson/linux-arm64/package.json`
- **Package**（package_manifest）：{ "name": "continue-binary", "version": "1.0.0", "description": "", "bin": "../../out/index.js", "pkg": { "scripts": "node modules/axios/ / " , "assets": "../../../core/node modules/sqlite3/ / ", "../../out/tree-sitter.wasm", "../../out/tree-sitter-wasms/ ", "../../tree-sitter/ / ", "../../out/llamaTokenizer.mjs", "../../out/llamaTokenizerWorkerPool.mjs", "../../out/tiktokenWorkerPool.mjs", "../../out/package.json" , "targets": "node18-linux-x64" , "outputPath": "bin" }, "author": "", "license": "Apache-2.0" } 证据：`binary/pkgJson/linux-x64/package.json`
- **Package**（package_manifest）：{ "name": "continue-binary", "version": "1.0.0", "description": "", "bin": "../../out/index.js", "pkg": { "scripts": "node modules/axios/ / " , "assets": "../../../core/node modules/sqlite3/ / ", "../../out/tree-sitter.wasm", "../../out/tree-sitter-wasms/ ", "../../tree-sitter/ / ", "../../node modules/win-ca/lib/crypt32-ia32.node", "../../node modules/win-ca/lib/crypt32-x64.node", "../../node modules/win-ca/lib/roots.exe", "../../out/llamaTokenizer.mjs", "../../out/llamaTokenizerWorkerPool.mjs", "../../out/tiktokenWorkerPool.mjs", "../../out/package.json" , "targets": "node18-win-arm64" , "outputPath": "bin" }, "author": "", "license": "Apache-2.0" } 证据：`binary/pkgJson/win32-arm64/package.json`
- **Package**（package_manifest）：{ "name": "continue-binary", "version": "1.0.0", "description": "", "bin": "../../out/index.js", "pkg": { "scripts": "node modules/axios/ / " , "assets": "../../../core/node modules/sqlite3/ / ", "../../out/tree-sitter.wasm", "../../out/tree-sitter-wasms/ ", "../../tree-sitter/ / ", "../../node modules/win-ca/lib/crypt32-ia32.node", "../../node modules/win-ca/lib/crypt32-x64.node", "../../node modules/win-ca/lib/roots.exe", "../../out/llamaTokenizer.mjs", "../../out/llamaTokenizerWorkerPool.mjs", "../../out/tiktokenWorkerPool.mjs", "../../out/package.json" , "targets": "node18-win-x64" , "outputPath": "bin" }, "author": "", "license": "Apache-2.0" } 证据：`binary/pkgJson/win32-x64/package.json`
- **Package**（package_manifest）：{ "name": "@xenova/transformers", "version": "2.14.0", "description": "State-of-the-art Machine Learning for the web. Run 🤗 Transformers directly in your browser, with no need for a server!", "main": "./src/transformers.js", "types": "./types/transformers.d.ts", "type": "module", "scripts": { "typegen": "tsc ./src/transformers.js --allowJs --declaration --emitDeclarationOnly --declarationMap --outDir types", "dev": "webpack serve --no-client-overlay", "build": "webpack && npm run typegen", "generate-tests": "python -m tests.generate tests", "test": "node --experimental-vm-modules node modules/jest/bin/jest.js --verbose --maxConcurrency 1", "readme": "python ./docs/scripts/build readme.py",… 证据：`core/vendor/modules/@xenova/transformers/package.json`
- **Package**（package_manifest）：{ "name": "vendor", "version": "1.0.0", "description": "", "main": "index.js", "scripts": { "test": "echo \"Error: no test specified\" && exit 1" }, "author": "", "license": "Apache-2.0", "dependencies": { "@xenova/transformers": "^2.14.0" }, "engine-strict": true, "engines": { "node": " =20.20.1" } } 证据：`core/vendor/package.json`
- **Package**（package_manifest）：{ "name": "@continuedev/cli", "version": "0.0.0-dev", "description": "Continue CLI", "main": "dist/index.js", "types": "dist/index.d.ts", "type": "module", "bin": { "cn": "dist/cn.js" }, "scripts": { "test": "vitest run", "test:watch": "vitest watch", "test:ui": "vitest --ui", "test:e2e": "vitest run --config vitest.e2e.config.ts", "test:smoke": "node smoke-test.mjs", "test:smoke-api": "vitest run --config vitest.smoke-api.config.ts", "build:tsc": "tsc -p tsconfig.build.json", "build:local-deps": "cd ../../packages/config-types && npm i && npm run build && cd ../fetch && npm i && npm run build && cd ../llm-info && npm i && npm run build && cd ../terminal-security && npm i && npm run build &… 证据：`extensions/cli/package.json`
- **Package**（package_manifest）：{ "name": "continue", "icon": "media/icon.png", "author": "Continue Dev, Inc", "version": "1.3.39", "repository": { "type": "git", "url": "https://github.com/continuedev/continue" }, "extensionKind": "ui", "workspace" , "bugs": { "url": "https://github.com/continuedev/continue/issues", "email": "nate@continue.dev" }, "homepage": "https://continue.dev", "qna": "https://github.com/continuedev/continue/issues/new/choose", "license": "Apache-2.0", "displayName": "Continue - open-source AI code agent", "pricing": "Free", "description": "The leading open-source AI code agent", "publisher": "Continue", "engines": { "vscode": "^1.70.0", "node": " =20.20.1" }, "engine-strict": true, "galleryBanner":… 证据：`extensions/vscode/package.json`
- **Package**（package_manifest）：{ "name": "my-react-project", "version": "1.0.0", "description": "A React project using Radix UI for accessible components", "main": "index.js", "scripts": { "start": "react-scripts start", "build": "react-scripts build", "test": "react-scripts test", "eject": "react-scripts eject" }, "keywords": "react", "radix-ui", "accessibility", "frontend" , "author": "Your Name", "license": "MIT", "dependencies": { "@radix-ui/react-accordion": "^1.0.0", "@radix-ui/react-alert-dialog": "^1.0.0", "@radix-ui/react-checkbox": "^1.0.0", "react": "^18.0.0", "react-dom": "^18.0.0", "react-scripts": "^5.0.0" }, "devDependencies": { "@types/react": "^18.0.0", "@types/react-dom": "^18.0.0", "typescript": "^4.5.… 证据：`manual-testing-sandbox/nested-folder/package.json`
- **Package**（package_manifest）：{ "name": "@continuedev/config-types", "version": "1.0.14", "description": "", "main": "dist/index.js", "types": "dist/index.d.ts", "type": "module", "scripts": { "test": "echo 'No tests to run'", "build": "tsc" }, "author": "Nate Sesti and Ty Dunn", "license": "Apache-2.0", "devDependencies": { "@types/node": "^20.11.19", "typescript": "^5.5.2" }, "dependencies": { "zod": "^3.25.76" } } 证据：`packages/config-types/package.json`
- **Package**（package_manifest）：{ "name": "@continuedev/config-yaml", "version": "1.23.0", "description": "", "main": "dist/index.js", "types": "dist/index.d.ts", "type": "module", "exports": { ".": { "browser": "./dist/browser.js", "node": "./dist/index.js", "default": "./dist/index.js" } }, "bin": { "config-yaml": "./dist/cli.js" }, "scripts": { "test": "cross-env NODE OPTIONS=--experimental-vm-modules jest", "build": "tsc", "generate-schema": "tsc && node dist/scripts/generateJsonSchema.js" }, "author": "Continue Dev, Inc.", "license": "Apache-2.0", "dependencies": { "@continuedev/config-types": "^1.0.14", "yaml": "^2.8.2", "zod": "^3.25.76" }, "devDependencies": { "@types/jest": "^29.5.14", "@types/node": "^20.0.0", "… 证据：`packages/config-yaml/package.json`
- **Package**（package_manifest）：{ "name": "@continuedev/sdk-generator", "version": "0.0.1", "description": "SDK Generator for Continue.dev", "type": "module", "scripts": { "build": "echo 'No build step needed'", "test": "echo 'No tests to run'", "generate-client:typescript": "openapi-generator-cli generate -i ./openapi.yaml -g typescript-fetch -o ./typescript/api -c ./openapi-generator-config.json", "generate-client:python": "openapi-generator-cli generate -i ./openapi.yaml -g python -o ./python/api -c ./openapi-generator-config.json", "generate-client:ALL": "npm run generate-client:typescript && npm run generate-client:python", "swagger-ui": "node swagger-ui-server.js" }, "author": "Continue Dev, Inc.", "license": "Apach… 证据：`packages/continue-sdk/package.json`
- **Package**（package_manifest）：{ "name": "@continuedev/hub-api", "version": "0.0.1", "description": "OpenAPI client for @continuedev/hub-api", "author": "OpenAPI-Generator", "repository": { "type": "git", "url": "https://github.com/GIT USER ID/GIT REPO ID.git" }, "main": "./dist/index.js", "typings": "./dist/index.d.ts", "module": "./dist/esm/index.js", "sideEffects": false, "scripts": { "build": "tsc && tsc -p tsconfig.esm.json", "prepare": "npm run build" }, "devDependencies": { "typescript": "^4.0 ^5.0" } } 证据：`packages/continue-sdk/typescript/api/package.json`
- **Package**（package_manifest）：{ "name": "@continuedev/sdk", "version": "0.0.13", "description": "SDK for Continue.dev", "main": "dist/src/index.js", "types": "dist/src/index.d.ts", "type": "module", "scripts": { "build": "bash ./build.sh", "test": "node --experimental-vm-modules node modules/jest/bin/jest.js", "test:watch": "node --experimental-vm-modules node modules/jest/bin/jest.js --watch" }, "author": "Continue Dev, Inc.", "license": "Apache-2.0", "dependencies": { "openai": "^4.104.0" }, "devDependencies": { "@types/jest": "^29.5.14", "dotenv": "^16.5.0", "jest": "^29.7.0", "ts-jest": "^29.1.2", "typescript": "^5.0.0" }, "files": "dist" } 证据：`packages/continue-sdk/typescript/package.json`
- **Package**（package_manifest）：{ "name": "@continuedev/fetch", "version": "1.1.0", "description": "", "main": "dist/index.js", "types": "dist/index.d.ts", "type": "module", "scripts": { "test": "vitest run", "build": "tsc" }, "author": "Nate Sesti and Ty Dunn", "license": "Apache-2.0", "dependencies": { "@continuedev/config-types": "^1.0.14", "follow-redirects": "^1.15.6", "http-proxy-agent": "^7.0.2", "https-proxy-agent": "^7.0.5", "node-fetch": "^3.3.2" }, "devDependencies": { "@types/follow-redirects": "^1.14.4", "typescript": "^5.0.0", "vitest": "^3.2.0", "@semantic-release/changelog": "^6.0.3", "@semantic-release/git": "^10.0.1", "@semantic-release/github": "^9.2.6", "@semantic-release/npm": "^13.1.5", "semantic-rel… 证据：`packages/fetch/package.json`
- **Package**（package_manifest）：{ "name": "@continuedev/hub", "version": "0.0.7", "description": "", "main": "dist/index.js", "types": "dist/index.d.ts", "type": "module", "scripts": { "test": "cross-env NODE OPTIONS=--experimental-vm-modules jest --passWithNoTests", "build": "tsc" }, "author": "Continue Dev, Inc.", "license": "Apache-2.0", "dependencies": { "@continuedev/config-yaml": "^1.38.0", "js-yaml": "^4.1.1" }, "devDependencies": { "@types/jest": "^29.5.14", "cross-env": "^7.0.3", "jest": "^29.7.0", "ts-jest": "^29.2.3", "ts-node": "^10.9.2" } } 证据：`packages/hub/package.json`
- **Package**（package_manifest）：{ "name": "@continuedev/llm-info", "version": "1.0.10", "description": "", "main": "dist/index.js", "types": "dist/index.d.ts", "type": "module", "scripts": { "test": "echo 'No tests to run'", "build": "tsc" }, "author": "Nate Sesti and Ty Dunn", "license": "Apache-2.0", "devDependencies": { "@types/node": "^22.15.29", "typescript": "^5.5.2", "@semantic-release/changelog": "^6.0.3", "@semantic-release/git": "^10.0.1", "@semantic-release/github": "^9.2.6", "@semantic-release/npm": "^13.1.5", "semantic-release": "^24.2.7" }, "overrides": { "picomatch": "^4.0.4" } } 证据：`packages/llm-info/package.json`
- **Package**（package_manifest）：{ "name": "@continuedev/openai-adapters", "version": "1.32.0", "description": "", "main": "dist/index.js", "types": "dist/index.d.ts", "type": "module", "scripts": { "test": "vitest", "build": "tsc" }, "author": "Nate Sesti and Ty Dunn", "license": "Apache-2.0", "dependencies": { "@ai-sdk/anthropic": "^3.0.44", "@ai-sdk/google": "^3.0.30", "@ai-sdk/deepseek": "^2.0.20", "@ai-sdk/openai": "^3.0.29", "@ai-sdk/xai": "^3.0.57", "@anthropic-ai/sdk": "^0.67.0", "@aws-sdk/client-bedrock-runtime": "^3.931.0", "@aws-sdk/credential-providers": "^3.974.0", "@continuedev/config-types": "^1.0.14", "@continuedev/config-yaml": "^1.38.0", "@continuedev/fetch": "^1.6.0", "@google/genai": "^1.30.0", "ai": "^… 证据：`packages/openai-adapters/package.json`
- **Package**（package_manifest）：{ "name": "@continuedev/terminal-security", "version": "1.0.0", "description": "Terminal command security evaluation for Continue", "main": "dist/index.js", "types": "dist/index.d.ts", "type": "module", "scripts": { "test": "vitest run", "test:watch": "vitest watch", "build": "tsc", "clean": "rm -rf dist" }, "author": "Continue Dev, Inc", "license": "Apache-2.0", "devDependencies": { "@types/node": "^20.11.19", "@types/shell-quote": "^1.7.5", "typescript": "^5.5.2", "vitest": "^3.2.4" }, "dependencies": { "shell-quote": "^1.8.1" } } 证据：`packages/terminal-security/package.json`
- **Docs Style Guide**（skill_instruction）：- Be concise — no filler. Make it easy to find what you're looking for - Task-oriented — frame around what the user is trying to do, not what the product can do - Progressive disclosure — guide from introduction to advanced use-cases. Don't throw users into the deep end - Real examples over abstract explanations — show, don't describe - Code snippets must be copy-pasteable — no placeholder values that silently break, no missing imports - Prerequisites up front — don't surprise the user halfway through - One topic per page — if you're covering two things, split it - Link, don't repeat — reference other docs instead of duplicating content - Scannable headings — skimming the TOC should reveal… 证据：`.claude/skills/docs-style/SKILL.md`
- **Contributing to Continue JetBrains extension**（documentation）：Contributing to Continue JetBrains extension 证据：`extensions/intellij/CONTRIBUTING.md`
- **Continue VS Code Extension**（documentation）：This is the Continue VS Code Extension. Its primary jobs are 证据：`extensions/vscode/CONTRIBUTING.md`
- **cn check — Local AI Agent Checks**（skill_instruction）：Run AI-powered code checks locally against your working tree changes using the Continue CLI. Each check is an agent defined in markdown that reviews your diff, identifies issues, and optionally suggests fixes as a patch. 证据：`skills/cn-check/SKILL.md`
- **Diff algorithm tests**（documentation）：--- is the delimeter, and surrounding whitespace will be trimmed. 证据：`core/diff/test-examples/README.md`
- 其余 20 条证据见 `AI_CONTEXT_PACK.json` 或 `EVIDENCE_INDEX.json`。

## 宿主 AI 必须遵守的规则

- **把本资产当作开工前上下文，而不是运行环境。**：AI Context Pack 只包含证据化项目理解，不包含目标项目的可执行状态。 证据：`docs/README.md`, `README.md`, `actions/README.md`
- **回答用户时区分可预览内容与必须安装后才能验证的内容。**：安装前体验的消费者价值来自降低误装和误判，而不是伪装成真实运行。 证据：`docs/README.md`, `README.md`, `actions/README.md`

## 用户开工前应该回答的问题

- 你准备在哪个宿主 AI 或本地环境中使用它？
- 你只是想先体验工作流，还是准备真实安装？
- 你最在意的是安装成本、输出质量、还是和现有规则的冲突？

## 验收标准

- 所有能力声明都能回指到 evidence_refs 中的文件路径。
- AI_CONTEXT_PACK.md 没有把预览包装成真实运行。
- 用户能在 3 分钟内看懂适合谁、能做什么、如何开始和风险边界。

---

## Doramagic Context Augmentation

下面内容用于强化 Repomix/AI Context Pack 主体。Human Manual 只提供阅读骨架；踩坑日志会被转成宿主 AI 必须遵守的工作约束。

## Human Manual 骨架

使用规则：这里只是项目阅读路线和显著性信号，不是事实权威。具体事实仍必须回到 repo evidence / Claim Graph。

宿主 AI 硬性规则：
- 不得把页标题、章节顺序、摘要或 importance 当作项目事实证据。
- 解释 Human Manual 骨架时，必须明确说它只是阅读路线/显著性信号。
- 能力、安装、兼容性、运行状态和风险判断必须引用 repo evidence、source path 或 Claim Graph。

- **Continue项目简介**：importance `high`
  - source_paths: README.md, core/core.ts, core/package.json
- **项目目录结构**：importance `high`
  - source_paths: core/package.json, gui/package.json, extensions/cli/package.json, packages/config-yaml/package.json
- **系统架构设计**：importance `high`
  - source_paths: core/core.ts, core/protocol/index.ts, binary/src/IpcIde.ts, binary/src/index.ts
- **通信协议与消息传递**：importance `medium`
  - source_paths: core/protocol/index.ts, core/protocol/webview.ts, core/protocol/ide.ts, core/protocol/messenger/index.ts, binary/src/IpcMessenger.ts
- **LLM集成架构**：importance `high`
  - source_paths: core/llm/index.ts, core/llm/llms/llm.ts, core/llm/templates/chat.ts, core/llm/streamChat.ts, core/llm/toolSupport.ts
- **模型提供商支持**：importance `high`
  - source_paths: core/llm/llms/index.ts, core/llm/llms/OpenAI.ts, core/llm/llms/Anthropic.ts, core/llm/llms/Ollama.ts, packages/openai-adapters/src/apis/OpenAI.ts
- **自动补全系统**：importance `high`
  - source_paths: core/autocomplete/CompletionProvider.ts, core/autocomplete/generation/CompletionStreamer.ts, core/autocomplete/templating/AutocompleteTemplate.ts, core/autocomplete/filtering/streamTransforms/StreamTransformPipeline.ts, core/autocomplete/context/ContextRetrievalService.ts
- **代码库索引系统**：importance `high`
  - source_paths: core/indexing/CodebaseIndexer.ts, core/indexing/CodeSnippetsIndex.ts, core/indexing/LanceDbIndex.ts, core/indexing/chunk/ChunkCodebaseIndex.ts, core/indexing/refreshIndex.ts

## Repo Inspection Evidence / 源码检查证据

- repo_clone_verified: true
- repo_inspection_verified: true
- repo_commit: `cb273098d968906d25ee737b454f0b5f13ea2482`
- inspected_files: `package.json`, `README.md`, `docs/package-lock.json`, `docs/troubleshooting.mdx`, `docs/reo-tracking.js`, `docs/faqs.mdx`, `docs/CONTRIBUTING.mdx`, `docs/c15t-cookie-banner.js`, `docs/index.mdx`, `docs/home.mdx`, `docs/package.json`, `docs/README.md`, `docs/reference.mdx`, `docs/docs.json`, `docs/overview.mdx`, `docs/cli/configuration.mdx`, `docs/cli/tool-permissions.mdx`, `docs/cli/headless-mode.mdx`, `docs/cli/tui-mode.mdx`, `docs/cli/quickstart.mdx`

宿主 AI 硬性规则：
- 没有 repo_clone_verified=true 时，不得声称已经读过源码。
- 没有 repo_inspection_verified=true 时，不得把 README/docs/package 文件判断写成事实。
- 没有 quick_start_verified=true 时，不得声称 Quick Start 已跑通。

## Doramagic Pitfall Constraints / 踩坑约束

这些规则来自 Doramagic 发现、验证或编译过程中的项目专属坑点。宿主 AI 必须把它们当作工作约束，而不是普通说明文字。

### Constraint 1: 来源证据：Terminal commands fail when `$SHELL` is set to `tcsh` due to hardcoded `-l` shell flag

- Trigger: GitHub 社区证据显示该项目存在一个安装相关的待验证问题：Terminal commands fail when `$SHELL` is set to `tcsh` due to hardcoded `-l` shell flag
- Host AI rule: 来源问题仍为 open，Pack Agent 需要复核是否仍影响当前版本。
- Why it matters: 可能增加新用户试用和生产接入成本。
- Evidence: community_evidence:github | cevd_823b2e0ae1ad49a78bd0a45d39a3099a | https://github.com/continuedev/continue/issues/12378 | 来源讨论提到 linux 相关条件，需在安装/试用前复核。
- Hard boundary: 不要把这个坑点包装成已解决、已验证或可忽略，除非后续验证证据明确证明它已经关闭。

### Constraint 2: 来源证据：The extension doesn't show up at all.

- Trigger: GitHub 社区证据显示该项目存在一个安装相关的待验证问题：The extension doesn't show up at all.
- Host AI rule: 来源显示可能已有修复、规避或版本变化，说明书中必须标注适用版本。
- Why it matters: 可能增加新用户试用和生产接入成本。
- Evidence: community_evidence:github | cevd_5d86070fe9d941ad9a44f1d09464b582 | https://github.com/continuedev/continue/issues/1312 | 来源讨论提到 windows 相关条件，需在安装/试用前复核。
- Hard boundary: 不要把这个坑点包装成已解决、已验证或可忽略，除非后续验证证据明确证明它已经关闭。

### Constraint 3: 来源证据：v1.0.67-jetbrains

- Trigger: GitHub 社区证据显示该项目存在一个配置相关的待验证问题：v1.0.67-jetbrains
- Host AI rule: 来源显示可能已有修复、规避或版本变化，说明书中必须标注适用版本。
- Why it matters: 可能增加新用户试用和生产接入成本。
- Evidence: community_evidence:github | cevd_4ce3fb2dde3d48978402a51bb56fbc99 | https://github.com/continuedev/continue/releases/tag/v1.0.67-jetbrains | 来源类型 github_release 暴露的待验证使用条件。
- Hard boundary: 不要把这个坑点包装成已解决、已验证或可忽略，除非后续验证证据明确证明它已经关闭。

### Constraint 4: 来源证据：v1.2.22-vscode

- Trigger: GitHub 社区证据显示该项目存在一个配置相关的待验证问题：v1.2.22-vscode
- Host AI rule: 来源显示可能已有修复、规避或版本变化，说明书中必须标注适用版本。
- Why it matters: 可能增加新用户试用和生产接入成本。
- Evidence: community_evidence:github | cevd_51004115b2b842e0afcd08792bdf1f61 | https://github.com/continuedev/continue/releases/tag/v1.2.22-vscode | 来源类型 github_release 暴露的待验证使用条件。
- Hard boundary: 不要把这个坑点包装成已解决、已验证或可忽略，除非后续验证证据明确证明它已经关闭。

### Constraint 5: 来源证据：v1.3.38-vscode

- Trigger: GitHub 社区证据显示该项目存在一个配置相关的待验证问题：v1.3.38-vscode
- Host AI rule: 来源显示可能已有修复、规避或版本变化，说明书中必须标注适用版本。
- Why it matters: 可能增加新用户试用和生产接入成本。
- Evidence: community_evidence:github | cevd_5f19fd622e784966a0747963ae1dc6ce | https://github.com/continuedev/continue/releases/tag/v1.3.38-vscode | 来源类型 github_release 暴露的待验证使用条件。
- Hard boundary: 不要把这个坑点包装成已解决、已验证或可忽略，除非后续验证证据明确证明它已经关闭。

### Constraint 6: 能力判断依赖假设

- Trigger: README/documentation is current enough for a first validation pass.
- Host AI rule: 将假设转成下游验证清单。
- Why it matters: 假设不成立时，用户拿不到承诺的能力。
- Evidence: capability.assumptions | github_repo:644686905 | https://github.com/continuedev/continue | README/documentation is current enough for a first validation pass.
- Hard boundary: 不要把这个坑点包装成已解决、已验证或可忽略，除非后续验证证据明确证明它已经关闭。

### Constraint 7: 维护活跃度未知

- Trigger: 未记录 last_activity_observed。
- Host AI rule: 补 GitHub 最近 commit、release、issue/PR 响应信号。
- Why it matters: 新项目、停更项目和活跃项目会被混在一起，推荐信任度下降。
- Evidence: evidence.maintainer_signals | github_repo:644686905 | https://github.com/continuedev/continue | last_activity_observed missing
- Hard boundary: 不要把这个坑点包装成已解决、已验证或可忽略，除非后续验证证据明确证明它已经关闭。

### Constraint 8: 下游验证发现风险项

- Trigger: no_demo
- Host AI rule: 进入安全/权限治理复核队列。
- Why it matters: 下游已经要求复核，不能在页面中弱化。
- Evidence: downstream_validation.risk_items | github_repo:644686905 | https://github.com/continuedev/continue | no_demo; severity=medium
- Hard boundary: 不要把这个坑点包装成已解决、已验证或可忽略，除非后续验证证据明确证明它已经关闭。

### Constraint 9: 存在安全注意事项

- Trigger: No sandbox install has been executed yet; downstream must verify before user use.
- Host AI rule: 转成明确权限清单和安全审查提示。
- Why it matters: 用户安装前需要知道权限边界和敏感操作。
- Evidence: risks.safety_notes | github_repo:644686905 | https://github.com/continuedev/continue | No sandbox install has been executed yet; downstream must verify before user use.
- Hard boundary: 不要把这个坑点包装成已解决、已验证或可忽略，除非后续验证证据明确证明它已经关闭。

### Constraint 10: 存在评分风险

- Trigger: no_demo
- Host AI rule: 把风险写入边界卡，并确认是否需要人工复核。
- Why it matters: 风险会影响是否适合普通用户安装。
- Evidence: risks.scoring_risks | github_repo:644686905 | https://github.com/continuedev/continue | no_demo; severity=medium
- Hard boundary: 不要把这个坑点包装成已解决、已验证或可忽略，除非后续验证证据明确证明它已经关闭。

