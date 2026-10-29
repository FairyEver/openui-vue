# openui-vue

OpenUI 的 Vue 3 实现，pnpm workspace monorepo。

## 技术栈

- Vue 3.5+、TypeScript strict、纯 ESM
- pnpm 10 管理 workspace，Node >= 20.19

## 目录结构

- `packages/*`：各发布包，包名统一为 `@openui-vue/<name>`
- `packages/example`：工作区模板包，仅用于验证构建链路，不是业务包
- 根 `tsconfig.json`：共享编译配置，包内 `tsconfig.json` 通过 `extends: "../../tsconfig.json"` 继承
- 根 `package.json`：只放私有脚本和共享开发依赖，不放业务代码

## 常用命令

```bash
pnpm install
pnpm build          # 递归执行各包 build
pnpm typecheck      # 递归执行各包 typecheck
pnpm --filter @openui-vue/<name> run <script>
```

## 新增包规范

- 目录：`packages/<name>`
- `package.json`：`name` 为 `@openui-vue/<name>`，`type: "module"`，`exports` 指向 `dist`，`files` 包含 `dist`
- `tsconfig.json`：继承根配置，设置 `rootDir: "src"`、`outDir: "dist"`
- 包之间通过包名互相引用，禁止用相对路径跨 `packages/` 目录导入
- 业务包默认 `private: false`，示例包保持 `private: true`

## 代码约定

- 只做完成当前任务必需的修改，不做无关重构或格式化
- 当前为最小工具链（仅 TypeScript），不要擅自引入 ESLint、Prettier、测试框架、构建器或发布工具
- 不提交 `dist/`、`node_modules/`、`.tsbuildinfo`

## 只读参考仓库

- `/Users/liyang/Documents/code/github/openui` 是上游 OpenUI（`thesysdev/openui`）的只读镜像，固定 `main` 分支
- 禁止在其中修改、新建、删除文件，禁止安装依赖、生成构建产物或提交
- 需要借鉴实现时只读查看，代码写入本仓库

## 验证要求

- 修改后至少运行受影响包的 `typecheck` 或 `build`
- 未实际执行的验证不得写成已通过
