# 量潮 GitHub 适配（quanttide-github）

量潮第二大脑适配轴（adapters/）的 GitHub 适配仓库。

## 定位

把 `domains/` 的领域知识转换成 GitHub 可消费的形态：负责接口包装、格式映射与运行时桥接，不生产领域事实，只做接通。

- 上游：`domains/` 领域知识
- 下游：GitHub

## 边界

GitHub 是**平台层**适配，管的是 GitHub 独有、换别的托管平台就不成立的部分：

- **归本仓库**：GitHub API 与鉴权（REST/GraphQL、PAT、App、OIDC）、协作对象（Pull Request、Review、Issues、CODEOWNERS、branch protection）、平台运维（Actions 语法与 runner 与 secrets、Packages、Pages、Releases 页）、组织与权限矩阵、配额与限制
- **不归本仓库**：Git 协议本身的通用概念（对象模型、分支与合并策略、提交规范与签名、子模块与 gitlink 条目）——那部分换任何托管都成立；GitLink 等其它托管平台的差异也各自归其平台适配器

三者关系：Git 协议层 → 本仓库（GitHub）／其它平台适配器，平台适配器之间互不依赖。

## 结构

| 路径 | 说明 |
|------|------|
| `data/context` | GitHub 适配语境 (git submodule → quanttide-context-of-github) |

其余随实现演进补充。

## 许可

[CC BY 4.0](LICENSE)
