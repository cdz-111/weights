# chief-weights

CHIEF 病理基础模型权重文件备份（Git LFS 托管）。

## 文件

| 文件 | 大小 | 说明 |
|---|---|---|
| `chief/CHIEF_CTransPath.pth` | 107 MB | CTransPath 视觉骨干 |
| `chief/CHIEF_pretraining.pth` | 4.6 MB | 预训练权重 |
| `chief/CHIEF_finetune.pth` | 2.6 MB | 微调权重 |
| `chief/Text_emdding.pth` | 58 KB | 文本嵌入 |

## 获取

```bash
# 需先安装 Git LFS
git lfs install
git clone https://github.com/cdz-111/chief-weights.git
```

未安装 Git LFS 时 clone 下来的 `.pth` 只是几百字节的指针文件，不可用。

## 来源

权重来自 CHIEF（A foundational model for computational pathology），原始发布见
[JSUNlab/CHIEF](https://github.com/hms-dbmi/CHIEF)。本仓库仅作个人下载备份，版权归原作者。

## 国内镜像

Gitee 同步一份：<https://gitee.com/cdz_yyds/chief-weights>

因 Gitee 社区版单文件上限 50MB 且无免费 LFS，`CHIEF_CTransPath.pth` 在那里被拆成 3 个分片，
clone 后需先执行 `cd chief && bash merge.sh` 合并再使用。
