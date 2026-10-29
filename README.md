# openui-vue

OpenUI 的 Vue 3 实现，基于 pnpm workspace 的 monorepo。

## 结构

```
packages/          各发布包，包名统一为 @openui-vue/<name>
packages/example/  工作区模板包（验证构建链路）
```

## 开发

```bash
pnpm install
pnpm build
pnpm typecheck
```

## 新增包

在 `packages/` 下新建目录，`package.json` 使用 `@openui-vue/<name>` 作为包名，并继承根 `tsconfig.json`。
