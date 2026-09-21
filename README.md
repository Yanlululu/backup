# 多智能体追逃与防御项目备份

保存于 2026-09-21。每个项目的默认版本放在 `main` 的独立目录中；原始提交历史保存在以项目名开头的独立分支中。分支指向原作者的同一个 Git 提交，目录的 Git tree 与对应原仓库一致，保留文件字节、路径大小写、文件模式、许可证和作者署名。

| 来源仓库 | 默认版本目录 | 原始历史分支 | 全部引用可达提交数 | 默认版本普通文件数 |
| --- | --- | --- | ---: | ---: |
| [ARBoids](https://github.com/taojy687/ARBoids) | [ARBoids](ARBoids/) | [`arboids/main`](https://github.com/Yanlululu/backup/tree/arboids/main) | 5 | 182 |
| [psto-aav-pursuit](https://github.com/HITSZ-MAS/psto-aav-pursuit) | [psto-aav-pursuit](psto-aav-pursuit/) | [`psto-aav-pursuit/main`](https://github.com/Yanlululu/backup/tree/psto-aav-pursuit/main) | 8 | 20 |
| [pursuitFSC2](https://github.com/LijunSun90/pursuitFSC2) | [pursuitFSC2](pursuitFSC2/) | [`pursuitFSC2/main`](https://github.com/Yanlululu/backup/tree/pursuitFSC2/main) | 7 | 621 |
| [pursuitMatrixWorld](https://github.com/LijunSun90/pursuitMatrixWorld) | [pursuitMatrixWorld](pursuitMatrixWorld/) | [`pursuitMatrixWorld/main`](https://github.com/Yanlululu/backup/tree/pursuitMatrixWorld/main) | 4 | 16 |
| [Multi-UAV-pursuit-evasion](https://github.com/thu-uav/Multi-UAV-pursuit-evasion) | [Multi-UAV-pursuit-evasion](Multi-UAV-pursuit-evasion/) | [`Multi-UAV-pursuit-evasion/master`](https://github.com/Yanlululu/backup/tree/Multi-UAV-pursuit-evasion/master) | 1115 | 160 |

提交数按每个来源仓库的全部公开引用去重统计；Multi-UAV 还包含两个 Git 子模块，未计入普通文件数。此备份不会自动同步原作者的后续更新。

## 论文与地址对应关系

- **psto-aav-pursuit**：2026 年《Decentralized End-to-End Multi-AAV Pursuit Using Predictive Spatio-Temporal Observation via Deep Reinforcement Learning》的官方实现，论文 [arXiv:2603.24238](https://arxiv.org/abs/2603.24238)。
- **pursuitFSC2**：2023 年《Toward multi-target self-organizing pursuit in a partially observable Markov game》的算法实现；**pursuitMatrixWorld** 是同作者提供的配套环境。论文 [arXiv:2206.12330](https://arxiv.org/abs/2206.12330)，预印本始于 2022 年，期刊发表于 2023 年。
- **Multi-UAV-pursuit-evasion**：2025 年《Online Planning for Multi-UAV Pursuit-Evasion in Unknown Environments Using Deep Reinforcement Learning》的实现，论文 [arXiv:2409.15866](https://arxiv.org/abs/2409.15866)。原 README 使用较早标题，链接论文的后续版本使用上述标题。备份时默认分支为 `master`。

## 分支、标签与历史

原分支 `refs/heads/<branch>` 保存为本仓库的 `<项目名>/<branch>`；ARBoids 使用 `arboids/main`。五个来源仓库在备份时均没有公开标签。

Multi-UAV 的全部分支为：

- [`Multi-UAV-pursuit-evasion/master`](https://github.com/Yanlululu/backup/tree/Multi-UAV-pursuit-evasion/master)
- [`Multi-UAV-pursuit-evasion/main`](https://github.com/Yanlululu/backup/tree/Multi-UAV-pursuit-evasion/main)
- [`Multi-UAV-pursuit-evasion/rebuttal`](https://github.com/Yanlululu/backup/tree/Multi-UAV-pursuit-evasion/rebuttal)

其公开 PR 引用 `refs/pull/11/head` 和 `refs/pull/11/merge` 分别保存在 `Multi-UAV-pursuit-evasion/pull/11/head` 与 `Multi-UAV-pursuit-evasion/pull/11/merge` 分支中。它们保留原 Git 提交，不会在本仓库创建新的 PR。

克隆单个项目及该分支的完整历史，例如：

```bash
git clone --single-branch --branch psto-aav-pursuit/main https://github.com/Yanlululu/backup.git psto-aav-pursuit
git clone --single-branch --branch pursuitFSC2/main https://github.com/Yanlululu/backup.git pursuitFSC2
git clone --single-branch --branch pursuitMatrixWorld/main https://github.com/Yanlululu/backup.git pursuitMatrixWorld
git clone --single-branch --branch Multi-UAV-pursuit-evasion/master https://github.com/Yanlululu/backup.git Multi-UAV-pursuit-evasion
```

上述 `--single-branch` 只限制获取哪个分支，不截断该分支的历史。如需本仓库全部分支，使用普通 `git clone`，不要添加 `--single-branch` 或 `--depth`。从 `main` 下载 ZIP 只包含目录快照和依赖包；Git 历史应通过克隆获取。

## Multi-UAV 的两个子模块

原 `.gitmodules` 指向 `btx0424/rl` 与 `btx0424/tensordict`。备份时 `btx0424/rl` 返回 404，但指定的同一 TorchRL 提交仍存在于官方 `pytorch/rl`。以下两个 bundle 均包含固定版本及其完整祖先历史，可以在没有原作者仓库的情况下恢复：

| 子模块 | 固定提交 | 下载来源 | 完整历史包 |
| --- | --- | --- | --- |
| TorchRL | `e39e70122600961d5830aa29027a073c0d721268` | [pytorch/rl](https://github.com/pytorch/rl) | [_git_bundles/torchrl.bundle](_git_bundles/torchrl.bundle) |
| TensorDict | `5e6205c2be7ebc75d1d0199f76fe7ff11f71d770` | [btx0424/tensordict](https://github.com/btx0424/tensordict) | [_git_bundles/tensordict.bundle](_git_bundles/tensordict.bundle) |

原始历史分支与目录快照中的 `.gitmodules` 保持原样。因此不要直接依赖其中已失效的地址执行递归克隆。以下命令适用于 Ubuntu/Bash；先把本仓库的 `main` 克隆到与 Multi-UAV 项目并列的 `backup` 目录：

```bash
git clone --single-branch --branch main https://github.com/Yanlululu/backup.git backup
cd Multi-UAV-pursuit-evasion
BUNDLE_DIR="$(cd ../backup/_git_bundles && pwd)"
git submodule init
git config submodule.third_party/torchrl.url "$BUNDLE_DIR/torchrl.bundle"
git config submodule.third_party/tensordict.url "$BUNDLE_DIR/tensordict.bundle"
git -c protocol.file.allow=always submodule update --init --recursive
git submodule status
```

仅本地 `.git/config` 改用 bundle 地址，原 `.gitmodules` 不变。初始化完成后，两个子模块应分别处于上表的固定提交。`main/Multi-UAV-pursuit-evasion/third_party/` 保留原 gitlink；子模块内容保存在上述 bundle 中。

## 保存范围

备份保留来源仓库在上述日期公开的 Git 文件、完整可达历史、分支和标签状态；已检查四个新增仓库的全部历史，没有 Git LFS 指针遗漏。Multi-UAV 两个子模块已额外保存。公开 Issues、PR 元数据和讨论以 JSON 存在 [_upstream_metadata](_upstream_metadata/) 中，属于静态资料，不会变成本仓库的在线 Issues/PR。

运行环境需要另行安装。Isaac Sim、PSTO 所依赖的外部 OmniDrones 安装，以及作者未公开上传的权重、数据或训练日志，不会因克隆而自动获得。此处完成的是代码和历史备份，尚未声明完成训练复现。

备份是独立副本，修改或删除本仓库不会修改原作者仓库。原作者后续改为私有或删除仓库，也不会撤回已经保存在此处的 Git 内容；使用和分发仍遵循各项目原许可证。
