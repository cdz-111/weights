# weights

个人模型权重集中仓。按模型分目录存放，一个模型一个目录，互不干扰。

## 目录索引

<!-- INDEX:START -->
| 目录 | 文件数 | 体积 | 分片 |
|---|---|---|---|
| `chief/` | 4 | 113.3 MB | — |
<!-- INDEX:END -->

## 各模型

### chief

CHIEF 病理基础模型权重，原始发布见 [JSUNlab/CHIEF](https://github.com/hms-dbmi/CHIEF)。

| 文件 | 大小 | 说明 |
|---|---|---|
| `CHIEF_CTransPath.pth` | 107 MB | CTransPath 视觉骨干 |
| `CHIEF_pretraining.pth` | 4.6 MB | 预训练权重 |
| `CHIEF_finetune.pth` | 2.6 MB | 微调权重 |
| `Text_emdding.pth` | 58 KB | 文本嵌入 |

## 获取

本仓大文件由 Git LFS 托管，**必须先装 Git LFS**，否则拿到的是几百字节的指针文件。

```bash
git lfs install
git clone https://github.com/cdz-111/weights.git
```

只取最新一份、不拉全部历史：

```bash
git clone --depth 1 https://github.com/cdz-111/weights.git
```

## 国内镜像

Gitee 同步一份：<https://gitee.com/cdz_yyds/weights>

Gitee 社区版限制单文件 50MB 且无免费 LFS，因此那边的 `>45MB` 文件会被切成 `40MB` 分片，
clone 后需要先合并：进入对应模型目录执行 `bash merge.sh`。

## 添加新模型

本地 `tools/add_weights.sh` 一条命令搞定两边（含自动分片、生成校验和与合并脚本）：

```bash
tools/add_weights.sh <模型名> <源目录或文件>...
```

只重建上面的索引表：

```bash
tools/add_weights.sh --rebuild-index
```

手工作业的话注意三点：GitHub 侧原样放、Gitee 侧超 45MB 要切片、每个模型目录自带
`SHA256SUMS` 与 `merge.sh`。

## 版权

各权重版权归其原作者所有，本仓仅作个人下载备份。
