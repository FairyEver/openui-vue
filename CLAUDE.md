@AGENTS.md

# Claude 补充说明

- 项目规则以 `AGENTS.md` 为准，本文件只补充 Claude 特有的工作方式。
- 当前仓库处于初始化阶段，新增能力前先确认属于哪个包，不要在根目录堆放业务代码。
- 用户使用 pnpm；不要用 npm 或 yarn 安装依赖，也不要生成 `package-lock.json` 或 `yarn.lock`。
- 涉及 Vue 运行时或组件实现时，先查只读参考仓库 `/Users/liyang/Documents/code/github/openui`，不要凭记忆编造 API。
- 交付时说明改动的文件、执行过的验证命令和结果；未验证的内容明确标注。
