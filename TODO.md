# TODO

本仓库的待办。**暂时不执行**，先记下来。

## 待定（需先定方向）

### 1. `quanttide-github-actions` 的归位

云端已有仓库 `quanttide-github-actions`（量潮 GitHub Actions），含两个可复用工作流：

- `jupyterbook-publish.yml`
- `pypi-publish.yml`

现状：既不在适配轴里，也没被任何父仓库引用。按本仓库的边界（GitHub 是平台层适配），它落在本仓库的职责范围内。两条路：

| 选项 | 做法 | 代价 |
|:--|:--|:--|
| 并进来 | 工作流移入本仓库 | 少一个仓库；但本仓库会同时承载「适配实现」与「可复用工作流」 |
| 独立保留 | 本仓库引用它 | 职责清晰；多一层引用 |

### 2. 其它托管平台的适配器

GitLink 等国内平台若要做，各设一个平台适配器，彼此独立、互不依赖。动手前要先解决两件事：

- **命名撞车**：`gitlink` 在 Git 里是专有名词——子模块指针那种 `mode 160000` 条目就叫 gitlink，而量潮架构处处依赖它。平台适配器要么换一个不撞车的名字，要么在文档里把「gitlink 条目」与「GitLink 平台」显式区分。
- **哪些平台真要做**：没有真实使用场景的平台不先建。

### 3. 流水线的语义与语法分界

按适配轴的规则：

- 流水线的**阶段与门禁**（质量门 → 发布 → 补 Release）是方法，归领域 `domains/quanttide-devops`
- 流水线的**语法与执行**（YAML、runner、secrets、矩阵）是平台接口，归本仓库

这条分界目前只存在于讨论中，尚未落到任一仓库的文档。

## 可动手

（暂无）

## 已定，不在此列

- `quanttide-git` **不创建**——适配器接的是外部系统，Git 是工具与协议，不是外部系统；其用法归 `domains/quanttide-devops` 与 `assets/quanttide-specification`。理由见 [README](README.md) 的「边界」一节。
