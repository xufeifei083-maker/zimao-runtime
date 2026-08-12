# 紫猫固定 Runtime

本仓库用于公开发布紫猫固定版本的 ComfyUI、Python、PyTorch、CUDA Runtime 和 FFmpeg 运行环境清单。

首个 Runtime ID 预定为：

```text
win-nvidia-h3-2026.08.1
```

当前仓库只建立发布规范，尚未发布 Runtime 二进制。只有完成干净机器安装、8 GB 显存 / 16 GB 内存门槛测试、文件哈希和 Ed25519 签名后，才会创建正式 GitHub Release。

## 发布物

正式 Release 应包含：

- `runtime-manifest.json`
- `runtime-manifest.sig`
- `checksums.sha256`
- `runtime-<version>.partNN` 分卷

Runtime 清单必须符合 [`runtime-manifest.schema.json`](runtime-manifest.schema.json)，发布步骤见 [`RELEASE-CHECKLIST.md`](RELEASE-CHECKLIST.md)。

本仓库不存放模型；工作流模型由软件从 Hugging Face 固定 commit 下载。
