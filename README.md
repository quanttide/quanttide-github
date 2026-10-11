# 量潮 GitHub 适配（quanttide-github）

量潮第二大脑适配轴（adapters/）的 GitHub 适配仓库。

## 定位

把 `domains/` 的领域知识转换成 GitHub 可消费的形态：负责接口包装、格式映射与运行时桥接，不生产领域事实，只做接通。

- 上游：`domains/` 领域知识
- 下游：GitHub

## 边界

GitHub 是**平台层**适配，管的是 GitHub 独有、换别的托管平台就不成立的部分：

- **归本仓库**：GitHub API 与鉴权（REST/GraphQL、PAT、App、OIDC）、协作对象（Pull Request、Review、Issues、CODEOWNERS、branch protection）、平台运维（Actions 语法与 runner 与 secrets、Packages、Pages、Releases 页）、组织与权限矩阵、配额与限制
- **不归本仓库**：Git 协议本身的通用概念（对象模型、分支与合并策略、提交规范与签名、子模块与 gitlink 条目）——那部分换任何托管都成立

为什么 Git 不单独设适配器：**适配器接的是外部系统，Git 不是外部系统**。Git 是工具与协议，它的用法属于领域知识与工程规范，归 `domains/quanttide-devops` 与 `assets/quanttide-specification`；只有 GitHub 这类**平台**（有账号、API、权限、配额）才需要一层接通。

其它托管平台（如有）各设一个平台适配器，各自独立，互不依赖。

## 结构

| 路径 | 说明 |
|------|------|
| `data/context` | GitHub 适配语境 (git submodule → quanttide-context-of-github-platform) |
| `examples/quanttide-github-lab` | GitHub 适配实验室 (git submodule → quanttide-github-lab) |

其余随实现演进补充。

## 许可

[CC BY 4.0](LICENSE)
